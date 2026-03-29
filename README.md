Task 1 :
#1.classification
-full name = Direct PII
-email = Direct PII
-date_of_birth = Indirect PII
-Zip_code = Indirect PII 
-job_title = Indirect PII
-diagnosis_notes = Sensitive PII

#2.Handling
-full name = drop
-email = drop
-date_of_birth =mask
-Zip_code = mask
-job_title = generalize
-diagnosis_notes = pseudonymize
