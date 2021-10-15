# News-Sensitivity-Detection

# README

### All the scripts described in this README file are located at work_yandex/Savannah/scripts. 
### They all serve the purpose of detecting the sensitivity of proper nouns. All python scripts are data cleaning: for proper nouns and for outlets ( and outlet types), and the last r file, main_analysis.r do the analysis part.


try_load_news.py: load sframe data from ‘work_yandex/res/prepared_news’, transfer it
to csv file and save as ‘work_yandex/res/prepare_news_dataframe.csv’
proper_counts.py: construct a csv file with only columns ‘propers’ and ‘proper-counts’
from ‘work_yandex/res/prepared_news’, and save as
‘work_yandex/Savannah/data/proper_counts/proper_counts.csv’

proper_sparse.py: construct sparse matrix(row: each news; columns: counts of proper
noun) ‘work_yandex/Savannah/data/proper_counts/proper_sparse’ and dictionary(two
columns: id,words) ‘work_yandex/Savannah/data/proper_counts/proper_dict.csv’ from
‘work_yandex/Savannah/data/proper_counts/proper_counts.csv’.

outlet_counts.py: (similar function with proper_counts but for outlet) construct a csv
file with only column ‘name_short’ (i.e. column with outlet name) from
‘work_yandex/res/prepared_news’, and save as
‘work_yandex/Savannah/data/outlet/outlet_counts.csv’

outlet_sparse.py (similar function with proper_sparse.py but for outlet) construct
sparse matrix(row: each news; columns: counts of proper noun) and save it in both a
csr sparse matrix format (prepared for main_analysis.r) at
‘work_yandex/Savannah/data/outlet/outlet_counts_matrix’ and a csv format at
‘work_yandex/Savannah/data/outlet/outlet_counts.csv’

outlet_types.py: construct ‘work_yandex/Savannah/data/outlet/df_type.csv’ where first
column is outlet name and second column outlet type and rows corresponding to rows
in all other files derives from the prepare_news_dataframe.csv.

Main_analysis.r: detect sensitive words and save distributions. Taking all the matrix
described above as inputs:
‘work_yandex/Savannah/data/proper_counts/proper_dict.csv’ as df_cocab_proper;
‘work_yandex/Savannah/data/outlet/outlet_counts_matrix’ as
matrix_counts_proper_outlets and ‘work_yandex/Savannah/data/outlet/df_type.csv’ as
df_types, saved output at ‘work_yandex/Savannah/data/ranking_results_1_boot.rds’


In the end, feel free to reach me (rw2840@columbia.edu) if you have any questions
regarding the scripts.
