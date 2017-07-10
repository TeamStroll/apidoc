# DTOs

## ResultsRequestDTO
Parameter | Type | Description
--------- | ------- | -----------
Bilateral| Boolean | Indicates if the procedure is bilateral.
CPT Code Id | String | Identifies the type of procedure.
User Id | Number | Id for logged in users.
Lat | Number | User's Latitude position.
Lng | Number | User's Longitude position.
Zip Code | String | User's zip code.
Payer Id | Number | Unique Id corresponding to the payer.
Plan Id | String | Unique Id corresponding to the plan.
Pricing Exception | String | If needed with CPT code, this indicates what possible pricing exceptions are included.
Quantity | Number | Number of procedures.

=======
## faxRequestDTO
faxRequestDTO Parameter | Type | Description
--------- | ------- | -----------
appointment | Object | A data transfer object containing appointment information
chosenFacilityId | Number | The Id that corresponds to an imaging facility.
costDTO | Object | A data transfer object containing cost information
cptCode | String | The CPT code that corresponds to the selected procedure.
createDateAsString | String | The current date formatted YYYY-MM-DD.
currentFacilityId | Number | The Id that corresponds with
facilityFaxRequestType | Number | 0 = FaxToPatient, 1 = FaxToPhysician, 2 = FaxToFacility, 3 = FaxToClaimAdministratorCompany, 4 = FaxToClaimAdministrator, 5 = FaxToSpecialist
faxDTO | Object | A data transfer object containing fax information
patientEmail | String | The patient's emails.
patientFaxRequestType | Number |
patientFirstName | String | The patient's first name.
patientId | Number | the Id that corresponds to the patient
patientLastName | String | The patient's last name.
patientPhoneNumber | String | The patient's phone number
physicianFaxRequestType | Number |
practiceId | Number | Id corresponding to the practice.
referringPhysicianId | Number | Id corresponding to the referring physician
referringPhysicianName | String | The name of the referring physician.
sendFaxToFacility | Boolean | Indicates if the fax is sent to the facility.
sendFaxToPatient | Boolean | Indicates if the fax is sent to the patient.
sendFaxToPhysician | Boolean | Indicates if the fax is sent to the physician.
userId | Number | Id corresponding to the user

## faxDTO
faxDTO Parameter | Type | Description
--------- | ------- | -----------
cash_alert | String | Indicates if the patient is paying with cash
cell_checkbox | Boolean |
claustrophobic_checkbox | Boolean | Indicates if the patient is claustrophobic
clinical_indication | String |
comparison_study_checkbox | Boolean |
courier_films_checkbox | Boolean |
courier_films_to_address | String |
courier_films_to_name | String |
cpt_code | String | CPT code for the procedure
creatinine | String |
creatinine_date | String |
diabetes_checkbox | Boolean | Indicates if the patient has diabetes
dob | String |
estimate_out_of_pocket_cost | String |
facility_address_1 | String |
facility_address_2 | String |
facility_address_3 | String |
facility_fax | String |
facility_name | String |
facility_phone | String |
fax_STAT_checkbox | Boolean |
fax_written_report_checkbox | Boolean |
female_checkbox | Boolean |
home_checkbox | Boolean |
icd9_code | String | ICD-9-CM medical diagnosis code
icd10_code | String | ICD-10-CM medical diagnosis code
insurance_carrier | String |
iv_contrast_allergy_checkbox | Boolean |
iv_contrast_allergy_description | String |
male_checkbox | Boolean |
medication_provided_checkbox | Boolean |
medication_provided_description | String |
member_ID | String |
office_checkbox | Boolean |
oral_contrast_allergy_checkbox | Boolean |
oral_contrast_allergy_description | String |
other_allergies_checkbox | Boolean |
other_allergies_description | String |
other_implanted_metal_checkbox | Boolean |
other_implanted_metal_description | String |
pacemaker_checkbox | Boolean |
pacemaker_description | String |
patientEmail | String |
patientFirstName | String |
patientLastName | String |
patient_name | String |
patient_phone_number | String |
phone_STAT_checkbox | Boolean |
phone_call_report_checkbox | Boolean |
physician_portal_checkbox | Boolean |
physician_portal_url | String |
practiceId | Number |
pregnant_checkbox | Boolean |
previous_MRIMRA_checkbox | Boolean |
previous_MRIMRA_date | String |
primary_language | String |
prior_auth_number | String |
procedure_locations | String |
procedure_short_description | String |
received_prior_auth_checkbox | Boolean |
referral_date | String |
referring_physician_NPI | String |
referring_physician_fax | String |
referring_physician_name | String |
referring_physician_phone | String |
referring_physician_signature | String |
renal_disease_checkbox | Boolean |
send_CD_checkbox | Boolean |
send_films_checkbox | Boolean |
send_patient_with_CD_checkbox | Boolean |
send_patient_with_films_checkbox | Boolean |
special_instructions | String |
symptom_onset_date | String |
taking_metformin_checkbox | Boolean |
userId | Number |
