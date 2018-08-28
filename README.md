# icd10_2018

# Some helpful commands
for n in A B C D E F G H I J K L M N O P Q R S T U V W X Y Z; do mkdir -p med-repo/$n; done
cat codes.csv | awk -F, '{tmp = "med-repo/"substr($1,1,1)"/med-proto-"$3".md"; print $0 > tmp; close(tmp)}'

for n in `find med-repo -type f`; do cat $n | awk -F\" '{print "# Category title: "$6"\n\
nAbbreviated description: "$2"\n\nFull description: "$4"\n"}' >> $n ; cat templates/protocol-body.txt >> $n; done
