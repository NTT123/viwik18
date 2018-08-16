# viwik18 dataset

Clean Vietnamese Text - Wikipedia dump 08-2018

Alphabet: aáàảãạăaáàảãạăắằẳẵặâấầẩẫậbcdđeéèẻẽẹêếềểễệfghiíìỉĩịjklmnoóòỏõọôốồổỗộơớờởỡợpqrstuúùủũụưứừửữựvwxyýỳỷỹỵz

## Merge to single file

        $ cat dataset/viwik18_* > viwik18.txt

## Generate the dataset manually

        $ wget https://dumps.wikimedia.org/viwiki/20180801/viwiki-20180801-pages-articles.xml.bz2
        $ bzip2 -d viwiki-20180801-pages-articles.xml.bz2
        $ python WikiExtractor.py --no-templates -s --lists viwiki-20180801-pages-articles.xml -q -o - | perl -CSAD -Mutf8 cleaner.pl > viwik18.txt


