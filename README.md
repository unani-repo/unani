# icd10_2018

# Some helpful commands
cat codes.csv | awk -F, '{tmp = "med-repo/"substr($1,1,1)"/med-proto-"$1"."$2".md"; print $0 > tmp; close(tmp)}'
