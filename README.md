# viwik19 dataset

Clean Vietnamese Text - Wikipedia dump 2019 (latest)

## Merge to single file

        $ cat dataset/viwik19_* > viwik19.txt

## Generate the dataset manually

        $ wget https://dumps.wikimedia.org/viwiki/latest/viwiki-latest-pages-articles.xml.bz2
        $ bzip2 -d viwiki-latest-pages-articles.xml.bz2
        $ python WikiExtractor.py --no-templates -s --lists viwiki-latest-pages-articles.xml -q -o - | perl -CSAD -Mutf8 cleaner.pl > viwiklatest.txt


