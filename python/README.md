

# build the 'filter' parameter
filter_by_institution_id = 'institutions.ror:https://ror.org/02y3ad647'
filter_by_paratext = 'is_paratext:false'
filter_by_type = 'type:journal-article'
filter_by_publication_date = 'from_publication_date:2012-07-31'

all_filters = (filter_by_institution_id, filter_by_paratext, filter_by_type, filter_by_publication_date)
filter_param = f'filter={",".join(all_filters)}'
print(f'filter query parameter:\n  {filter_param}')

# put the URL together
filtered_works_url = f'https://api.openalex.org/works?{filter_param}'
print(f'complete URL:\n  {filtered_works_url}')

group_by_param = 'group_by=is_oa'

work_groups_url = f'{filtered_works_url}&{group_by_param}'
print(f'complete URL with group_by:\n  {work_groups_url}')

import requests, json
response = requests.get(work_groups_url)
work_groups = response.json()['group_by']
print(json.dumps(work_groups, indent=2))

from num2words import num2words

open_works_count = 0
closed_works_count = 0
for index, group in enumerate(work_groups):
    print(f"--> The {num2words(index+1, ordinal=True)} group includes all works where `is_oa` is {group['key']} and has a count of {group['count']} publications.")
    
    if group['key']=="true":
        open_works_count += group['count']
    else: 
        closed_works_count += group['count']
    
total_works_count = open_works_count + closed_works_count
print('That makes an OA percentage of %f' % (100 * open_works_count/total_works_count))

import matplotlib.pyplot as plt
plt.rcParams["figure.figsize"] = (8,5.5)

# set labels and their respective values
groups = ['Open Access', 'Closed Access']
counts = [open_works_count, closed_works_count]
  
# some visual settings
colors = ['#23c552', '#f84f31']
explode = (0.01, 0.01)
  
# pie chart
plt.pie(counts, colors=colors, labels=groups,
        autopct='%1.1f%%', pctdistance=0.85,
        explode=explode, textprops={'fontsize': 14})
  
# make it a donut (draw circle in the middle)
centre_circle = plt.Circle((0, 0), 0.70, fc='white')
fig = plt.gcf()
fig.gca().add_artist(centre_circle)

# display chart
plt.show()
