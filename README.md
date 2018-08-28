# icd10_2018

# Some helpful commands
cat codes.csv | awk -F, '{print substr($1,1,1)"/med-proto-"$1"."$2".md"}'
