# icd10_2018

# Some helpful commands
for n in A B C D E F G H I J K L M N O P Q R S T U V W X Y Z; do mkdir -p med-repo/$n; done
cat codes.csv | awk -F, '{tmp = "med-repo/"substr($1,1,1)"/med-proto-"$3".md"; print $0 > tmp; close(tmp)}'

for n in `find med-repo -type f`; do cat $n | awk -F\" '{print "# Category title: "$6"\n\
nAbbreviated description: "$2"\n\nFull description: "$4"\n"}' >> $n ; cat templates/protocol-body.txt >> $n; done

# Disclaimer 1 :
The information in the document is not meant to be used first point of reference in any of the medical interventions.This is just a compilation of information for academic and knowledge purposes.

# Disclaimer 2 : 
Contributors are alone responsible for avoiding plagiarism or any other adverse effects. They indemnify the editors or originators of this page against any legal, financial or any other type of responsibility.The doc shared and prepared in the Open access will be in accordance with the "Open Access creative commons"  which can be reused. 
