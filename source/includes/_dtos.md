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
patientFaxRequestType | Number | 0 = FaxToPatient, 1 = FaxToPhysician, 2 = FaxToFacility, 3 = FaxToClaimAdministratorCompany, 4 = FaxToClaimAdministrator, 5 = FaxToSpecialist
patientFirstName | String | The patient's first name.
patientId | Number | the Id that corresponds to the patient
patientLastName | String | The patient's last name.
patientPhoneNumber | String | The patient's phone number
physicianFaxRequestType | Number | 0 = FaxToPatient, 1 = FaxToPhysician, 2 = FaxToFacility, 3 = FaxToClaimAdministratorCompany, 4 = FaxToClaimAdministrator, 5 = FaxToSpecialist
practiceId | Number | Id corresponding to the practice.
referringPhysicianId | Number | Id corresponding to the referring physician
referringPhysicianName | String | The name of the referring physician.
sendFaxToFacility | Boolean | Indicates if the fax is sent to the facility.
sendFaxToPatient | Boolean | Indicates if the fax is sent to the patient.
sendFaxToPhysician | Boolean | Indicates if the fax is sent to the physician.
userId | Number | Id corresponding to the user.

## faxDTO
faxDTO Parameter | Type | Description
--------- | ------- | -----------
cash_alert | String | Indicates if the patient is paying with cash.
cell_checkbox | Boolean | Indicates if the type of phone is a cell phone.
claustrophobic_checkbox | Boolean | Indicates if the patient is claustrophobic.
clinical_indication | String | The clinical indication for the procedure.
comparison_study_checkbox | Boolean | Indicates if the procedure is a comparison study.
courier_films_checkbox | Boolean | Indicates if results will be returned by courier film.
courier_films_to_address | String | The address the courier films will be sent to.
courier_films_to_name | String | Name of who receives the courier film.
cpt_code | String | CPT code for the procedure.
creatinine | String | Creatinine level.
creatinine_date | String | Date of when creatinine level were reported.
diabetes_checkbox | Boolean | Indicates if the patient has diabetes.
dob | String | Date of Birth of the patient.
estimate_out_of_pocket_cost | String | Cash pay estimate.
facility_address_1 | String | First line of facility address.
facility_address_2 | String | Second line of facility address.
facility_address_3 | String | Third line of facility address.
facility_fax | String | The facility fax number.
facility_name | String | The facility name.
facility_phone | String | The facility phone number.
fax_STAT_checkbox | Boolean | Indicates if the results are returned with fax STAT.
fax_written_report_checkbox | Boolean | Indicates if the results are returned with a fax written report.
female_checkbox | Boolean | Indicates if patient is female.
home_checkbox | Boolean | Indicates if the patients phone number is their home number.
icd9_code | String | ICD-9-CM medical diagnosis code.
icd10_code | String | ICD-10-CM medical diagnosis code.
insurance_carrier | String | Name of the patient's insurance carrier.
iv_contrast_allergy_checkbox | Boolean | Indicates if the patient has a IV contrast allergy.
iv_contrast_allergy_description | String | Describes the patient's IV allergy.
male_checkbox | Boolean | Indicates if the patient is male.
medication_provided_checkbox | Boolean | Indicates if medication was provided to the patient.
medication_provided_description | String | Name of medication provided.
member_ID | String | Id corresponding to the member.
office_checkbox | Boolean | Indicates if the patient phone number is an office phone.
oral_contrast_allergy_checkbox | Boolean | Indicates if the patient has oral contrast allergies.
oral_contrast_allergy_description | String | The patient's oral contrast allergy description
other_allergies_checkbox | Boolean | Indicates if the patient's have other allergies.
other_allergies_description | String | Description of the patient's other allergies.
other_implanted_metal_checkbox | Boolean | Indicates if the patient has other implants.
other_implanted_metal_description | String | Describes the other implants the patient has.
pacemaker_checkbox | Boolean | Indicates if the patient has a pacemaker.
pacemaker_description | String | Description of the pacemaker.
patientEmail | String | The patient's email.
patientFirstName | String | First name of patient.
patientLastName | String | Last name of patient.
patient_name | String | Name of the patient.
patient_phone_number | String | Patient phone number.
phone_STAT_checkbox | Boolean | Indicates if the results will be reported by phone STAT.
phone_call_report_checkbox | Boolean | Indicates if the results will be reported by phone call.
physician_portal_checkbox | Boolean | Whether the physician portal checkbox is checked
physician_portal_url | String | URL for the physician portal.
practiceId | Number | Id corresponding to the practice.
pregnant_checkbox | Boolean | Indicates if the patient is pregnant
previous_MRIMRA_checkbox | Boolean | Indicates if the patient previously had a MRI or MRA.
previous_MRIMRA_date | String | Date of the previous MRI or MRA
primary_language | String | Primary language of the physician.
prior_auth_number | String | Patient's prior authorization number.
procedure_locations | String | Location of the procedure.
procedure_short_description | String | A short description of the procedure.
received_prior_auth_checkbox | Boolean | Indicates if the patient received prior authorization.
referral_date | String | Date of the referral.
referring_physician_NPI | String | NPI corresponding to the referring physician.
referring_physician_fax | String | Referring physician fax number.
referring_physician_name | String | Referring physician name.
referring_physician_phone | String | Referring physician phone number.
referring_physician_signature | String | Id corresponding to the referring physician signature.
renal_disease_checkbox | Boolean | Indicates if the renal disease is prevalent.
send_CD_checkbox | Boolean | Indicates if a CD of the results is to be sent.
send_films_checkbox | Boolean | Indicates if the film of the results is to be sent.
send_patient_with_CD_checkbox | Boolean | Indicates if a CD of the results is to be sent with the patient.
send_patient_with_films_checkbox | Boolean | Indicates if the film of the results is to be sent with the patient.
special_instructions | String | Any special instructions.
symptom_onset_date | String | The date at which the symptoms onset.
taking_metformin_checkbox | Boolean | Indicates if the patient is taking metformin.
userId | Number | Id corresponding to the user.
