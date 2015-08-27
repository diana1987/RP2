# RP2
1. Creating word2vec model:
* Using MySQL database(Stefan's code):
user@servername:~/research_code$ python build_word2vec_model.py
This will generate : 

-rw-rw-r--  1 user user 11365675 Aug 10 11:32 word2vec_model_full_300D
-rw-rw-r--  1 user user 64786880 Aug 10 11:32 word2vec_model_full_300D.syn0.npy
-rw-rw-r--  1 user user 64786880 Aug 10 11:32 word2vec_model_full_300D.syn1.npy

***For the next step we first need to create a .csv file that will comprise the preprocessed posts***
File createCSV.py will do it. Then the output file has to be preprocessed with Martjin's code:
perl preprocessForumPosts.pl forum_post.csv  > outTokenizedPosts.csv

* Using a .csv file which will contain preprocessed data–lower-case and all the stopwords removed, as our database:
user@servername:~/research_code$ python makeCSVfile.py

At this step we will generate a CSV file format preprocessed


3.

./deepWords.py -a getvec -m <word2vec model> -c <file with posts>
./deepWords.py -a match -d <db file> -m <model> -q "a query post" -n <number of most similar posts>


4.

Keywords:

cat forum_post.csv | egrep -i 'cannabis|canabis|DMT|LSD|Mescaline|psilocybin' > unlabeled_set_soft_drugs

user@servername:~/research_code/keyword_search$ cat forum_post.csv | egrep -i 'unavailable site|ddos|site down' > unlabeled_set_hacking_ddos

user@servername:~/research_code/keyword_search$ cat forum_post.csv | egrep -i 'malware' > unlabeled_set_hacking_malware 

user@servername:~/research_code/keyword_search$ cat forum_post.csv | egrep -i 'cards|pin|card|atm' > unlabeled_set_financial_carding


user@servername:~/research_code/keyword_search$ cat forum_post.csv | egrep -i 'Bit|bitcoin|Block Chain|BTC|Cryptography|transactions|bitcoin miners| bitcoin mining| wallet| bitcoin network| private key' > unlabeled_set_bitcoins

user@servername:~/research_code/keyword_search$ cat forum_post.csv | egrep -i 'cards|pin|card|atm' > unlabeled_set_financial_carding
user@servername:~/research_code/keyword_search$ cat forum_post.csv | egrep -i 'gun|kill|hitman|order kill' > unlabeled_set_hitman



Count Lines:
wc -l 
Count words:
wc -w


https://bitcoin.org/en/vocabulary

Bit|bitcoin|Block Chain|BTC|Cryptography|transactions|bitcoin miners| bitcoin mining| wallet| bitcoin network| private key
