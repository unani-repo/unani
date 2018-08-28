# icd10_2018

# Some helpful commands
for n in A B C D E F G H I J K L M N O P Q R S T U V W X Y Z; do mkdir -p med-repo/$n; done
cat codes.csv | awk -F, '{tmp = "med-repo/"substr($1,1,1)"/med-proto-"$3".md"; print $0 > tmp; close(tmp)}'
