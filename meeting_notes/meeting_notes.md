**At our last meeting on 2/4, we discussed the** following:

1.       Attempted to assign OMOP drug exposure (drug type) concept id to Pcornet tables.  I have attached updated document from Don. 

> a.       Dispensing.  Used for claims data and third party  
>
> b.       Prescribing.  Data from Health systems.

2.       Question came up around whether we should include:

> a.       Medication List.  I believe we determined that this should not be included.
>
> b.      Patient reported.  

3.       Group will go back to their teams and review drug exposure type and description of rational used to partition source data into various types.

4.       Several codes were identified as NA.  Please see attached spreadsheet. 

I have attached two documents as follows:

·         Updated Drug exposure (drug type) concept id and mapping that we did last week.

·         Jim Singer (business analyst for NYC-CDRN) put the drug exposure table within the CDRN Conventions for Populating OMOP CDM V5 for Pcornet V3.  We can use this for our conversation tomorrow.

OMOP to PCORnet Meeting Notes 2/25/2016
=======================================

General agreement that "CDRN Conventions for Populating OMOP CDMv5 for PCORnetv3" changes proposed by Don i.e:

1.  Add biobank flag to Person table

2.  Add discharge disposition, discharge\_status, DRG and admitting source to Visit Occurrence

3.  Add diagnosis\_source to Condition Occurrence

should be pursued.

It was suggested that changes to Visit and Condition Occurrence tables should be proposed as additions OMOP CDM.

In preparation of writing a proposal to OHDSI community, the following tasks where given out. The idea is to search the OHDSI forums to see if there is already some discussion and to build up sufficient information to create use cases for adding attributes to CDM.

Rimma – to look at death, as an attribute to visit occurrence, the addition of death type and possibility of multiple death records.

Lisa to look at admission source and discharge disposition.

Don to look at condition source, e.g. admission, discharge

Rob to look at DRG for any discussion on OHDSI forums and maybe google search for interesting analysis done where DRG was a factor.

OMOP to PCORnet Meeting Notes 3/3/2016
======================================

In [*https://github.com/don-torok/OMOPv5-to-PCORnetv3*](https://github.com/don-torok/OMOPv5-to-PCORnetv3).  Had to make it public because otherwise someone needs to pay for private repository.  Not sure if that means other can commit changes or only see information.

Someone could try an edit and see if they can push result into remote repository.  Otherwise send me get names and I will grant update.  Also instead of the DrugExposure to PCORnet xls doc there is misc\_docs/OMOP to PCORnet3\_mapping.xls which has both the drugs and how we partitioned condition occurrence into diagnosis and condition tables.

Rimma your death issues doc is in same folder.

OMOP to PCORnet Meeting Notes 3/10/2016
=======================================

There is agreement that we have the latest OMOP conventions for PCORnet and OMOP to PCORnet ETL documents in github. <https://github.com/don-torok/OMOPv5-to-PCORnetv3>

Joan’s goto meeting account has expired, so that the meeting was by phone conversation only.

We determined that we should focus on the OMOP v5 to PCORnet v3 document first, since this will expose any element needed for PCORnet that are not already in OMOPv5. Then we can go back to the conventions document to determine how to address in OMOP.

Question: should reach out to other PCORi CDRNs to attend these meetings.

Two new documents are added to github.

1.  OMOP CDM Admission Source and Discharge Disposition.docx. Lisa reviewed the discharge disposition, discharge status and admitting source attributes and documented existing discussions from OHDSI that included these values.

2.  NY CDRN Excel workbook outlining differences between PCORnet v2 to v3 (still waiting for)

    Homework

<!-- -->

1.  Toan to pull ‘ETL from OMOP CDM v5 to PCORnet CDM v2.doc’ from github. Using this as a starting point, start new ETL document for OMOP CDMv5 to PCORnet v3. Add the PCORnet Prescribing and Condition tables and make a first pass at defining how these will be populated from OMOP CDMv5

2.  Don to go back to the ‘CDRN Conventions for Populating OMOP CDM v5 for PCORnet v3’ document and move the following attributes out from the Observation table

    -   Add biobank flag to Person table

    -   Add discharge disposition, discharge\_status, DRG and admitting source to Visit Occurrence

    -   Add diagnosis\_source to Condition Occurrence

<!-- -->

1.  Joan

    -   Get goto meeting account updated

    -   Resend NY CDRN document on PCORnet v2 to v3 differences

    -   Find NY CDRN contact for working group

2.  Rimma is going to work, in parallel, on a proposal for adding some of the attributes needed for PCORnet to the OMOP CDM.

OMOP to PCORnet Meeting Notes 3/17/2016
=======================================

Toan copied the original [ETL from *OMOP CDM v5 to PCORnet CDM v2.doc*](https://github.com/don-torok/OMOPv5-to-PCORnetv3/blob/v5_v3/OMOP5_to_PCORnet3/ETL%20from%20OMOP%20CDM%20v5%20to%20PCORnet%20CDM%20v2.doc) document to a [ *OMOP CDM v5 to PCORnet CDM v3.doc*](https://github.com/don-torok/OMOPv5-to-PCORnetv3/blob/v5_v3/OMOP5_to_PCORnet3/ETL%20from%20OMOP%20CDM%20v5%20to%20PCORnet%20CDM%20v2.doc) document and added the conventions to populate the Condition and Prescribing tables. He didn’t merge the change to the master branch but rather created a branch of the repository and added to document there. We can merge after the changes were reviewed. To see the newly added document, please select the v5\_v3 brand of the repository.

We discussed how to use GitHub as a repository for Word documents. Conclusion is that we as a group are not sure how to best use it. For now, it will be a read-only locations for all but the document owner. We should all probably do some home work on how git will handle MS Word documents.

As of now Toan owns ‘ETL from OMOP CDM v5 to PCORnet CDM v3.doc’

Don owns ‘OMOP to PCORnet Meeting Notes.docx’ & ‘CDRN Conventions for Populating OMOP CDM v5 for PCORnet v3.docx’

Lisa owns ‘OMOP CDM Admission Source and Discharge Disposition.docx’

There is no meeting next week because a number of people are going to AMIA.

**Homework**

All: Spend some time learning about git. See if the is a better way to use git with word documents.

Toan: Is going to add a table at the top of ‘ETL from OMOP CDM v5 to PCORnet CDM v3.doc’ that will list out the different sections and have a place for notes so that we can identify sections that need to be updated/added for PCORnetv3

Don/Rimma need to identify attributes that we think should be added to the OMOP CDM tables because they are important in their own right and they will help in conversion from OMOP to PCORnet.

OMOP to PCORnet Meeting Notes 4/07/2016
=======================================
Discussed result of OMOP meeting where Rimma proposed that OMOP should make the admission source, discharge disposition attributes in the visit occurrence table.  

Agreed that the DRG should be moved to the cost table.

The current proposed PCORnet conventions document is in https://github.com/don-torok/OMOPv5-to-PCORnetv3/blob/master/OMOP_conventions/CDRN%20Conventions%20for%20Populating%20OMOP%20CDM%20v5%20for%20PCORnet%20v3.docx

Started work on OMOP to PCORnet v3 document.  Added a table of changes that need to be addressed.

Homework:
Joan will find spreadsheet that list all difference between PCORnet v2 and v3 and distribute to group and Don will post to git repository.

Toan will continue work on OMOP to PCORnet v3 document adding item that need to be address.

Don change conventions document, put the DRG in the cost table after Rimma finds link describing the new OMOP cost table.

OMOP to PCORnet Meeting Notes 4/28/2016
================================================================
We reviewed the document "ETL from OMOP CDM v5 to PCORnet CDM v3", adding to the table list changes in PCORnet v3.

HomeWork
Don - add history an arrange directories in github.  Add previous versions of conventions and omop to pcornet


Meeting Notes May 5, 2016
=================================================================
Toan distributed 'TOBACCO and TOBACCO Type convention for PCORNet V3_ekb to.docx', which describes how to populate the PCORnet v3 columns **SMOKING**, **TOBACCO**, and **TOBACCO TYPE**  from the values listed in 'CDRN Conventions for Populating OMOP CDM v5 for PCORnet v3'.  Toan was not on hand to describe the document to the rest of the group.  Don had trouble reconciling concept id's in Toan's document to those listed in the CDRN conventions document.

As a group we looked at 'ETL from OMOP CDM v5 to PCORnet CDM v3' and determined that the sections that require changes.  A list of outstanding issues for the OMOPv4 to PCORnet v3 document is in a table starting on page two.

Latest documents posted to githup

Homework
Review 'ETL from OMOP CDM v5 to PCORnet CDM v3'.  Be prepared to fill in Death and Death Cause sections.

Meeting Notes May 12, 2016
=========================================================================

Dean Dean Calabrese will be taking over Joan Leavey's responsibilities for NYC CDRN.

We started a review of the document 'TOBACCO and TOBACCO Type convention for PCORNet V3_ekb to.docx' that Toan had distributed to the group.  The document proposes creating 3 observation type records that correspond to the PCORnet Vital fields Tobacco, Smoking and Tobacco type.  Toan proposed a logical partitioning of the tobacco related question into 3 categories Tobacco; Smoking and Tobacco Type. Where Tobacco answers if the person is a tobacco user, Smoking answers the frequency/amount of tobacco use; and Tobacco Type is used to describe the tobacco type used.

There was a question of how this new proposal relates to the previously defined conventions in 'CDRN Conventions for Populating OMOP CDM v5 for PCORnet v3.docx'

Don raised the question of why the concept relationship table is being used to link tobacco observations records together, arguing that the visit occurrence id and observation date are sufficient.

## Homework ##
Everyone
Review Toan's document 'TOBACCO and TOBACCO Type convention for PCORNet V3_ekb to.docx'. With an eye toward:

- Does the partitioning of tobacco related information into the three categories list above make sense and adequately cover possible responses.
- Are there better concept id's that can be used to represent the 3 categories.

Rob:
Create a quick document that explains how you have already implemented the tobacco related information at your site.

Rimma:
See how closely what we are planning aligns with any work OMOP is doing to capture tobacco related information in OMOP CDM.

## Next Week ##
Finish review of tobacco proposal.

Meeting Notes May 19, 2016
=============================================================================
Meeting called off because so few members dialed in.  The topic was to be conventions for tobacco related information.  Rob wrote up how he implemented the tobacco question in the OMOP CDM and how that is used to populate the vital entries in PCORNet v3.  The document, 'Tobacco Write Up_UCLA.docx' is in github under the misc_docs directory.

There is move to standardize how tobacco use information is recorded in OMOP.  Don is pessimistic that there will be consensus within the OMOP community any time soon and suggests that, for now, we follow Rob's implementation and then if/when OMOP agrees to a standard, we can change over to that implementation.

Meeting Notes May 26, 2016
===========================================================================================
At an earlier meeting where the goal was to define conventions for storing tobacco related information in the OMOP CDM, Rimma had presented an Excel Spread sheet that listed SNOMED related tobacco codes.  This spread sheet partitioned the codes into the following categories:

- Tobacco Non-User
- Tobacco Use Cessation Counseling
- Tobacco Use Cessation Pharmacotherapy
- Tobacco Use Screening
- Tobacco User
Within each of the above categories, there are defined a list of valid entries.  The scheme of representing this within OMOP CDM will be to assign an Observation Concept Id for each of the above categories and then use the value as concept id for recording the valid entries.

The first snag with this scheme is that there are not concepts for all categories listed above, but that can be solved.  The spread sheet does provide SNOMED Codes (and a few CPT code) for all the entries within the categories and it is assumed that the vocabulary does have concepts for all of these codes.

The spread sheet, SNOMED_smoking_concepts.xlsx, limited to just the tobacco related information, is posted in github https://github.com/don-torok/OMOPv5-to-PCORnetv3 under misc_docs.

## Homework##
Two things are necessary to determine if this scheme will be satisfactory 1) the first is to determine if the list of valid entries (the description column in the Excel doc) is sufficient to capture all the information we have seen in our source data and 2) to determine what is required to map the above list of concepts into the tobacco categories defined in PCORnet v3.  Users should try this exercise using the source data they are familiar with.


Meeting Notes June 2, 2016
===================================================================================
Still taking about tobacco.  But looks like we are coming closer to a consensus on how to represent the data in OMOP. The basic scheme is to use a single Observation Concept, Tobacco use and exposure (4041306) to group all of a patient's tobacco related findings. Then the specific values describing a person's tobacco history will be recorded in the value as concept id. The list of concepts to use for the value as concept id is to be defined.  The current list is in  https://github.com/don-torok/OMOPv5-to-PCORnetv3/misc_docs/OMOP_concept_for_smoking.xlsx.  The more concepts that can be eliminated from this list, while still remaining comprehensive enough to represent values found in the source data, the easier it will be to convert the possible combination into the PCORnet vital table values.

Meeting Notes June 9, 2016
=====================================================================================================
Just talking about tobacco may be the death of us.  We viewed an excel workbook with a list of concepts that we
believe are sufficient to cover the vast majority of potential answers to tobacco use and exposure values we are likely to see in the source data.  

We agreed that these values will be stored in the observation table
We agreed that for 'How many years did you smoke up to now' which is a LOINC code, the value as concept id would
hold the concept id for the LOINC code and that if the value representing years was numeric it would be stored in
value as number.

The next step after capturing all the data in OMOP is to determine how these values will map into the PCORnet vital table columns SMOKING, TOBACCO and TOBACCO TYPE.  This is being taken on as homework.

## Homework ##
Starting with the workbook 'OMOP_concept_for_smoking.xlsx' each person should work on how to map the possible OMOP values into PCORnet.
Meeting Notes June 16,2016
==============================================================================================================
Don presented his 'Possible Solution for Mapping OMOP Observation to PCORnet Vital Smoking'.  See "A Solution for Mapping OMOP Observation to PCORnet Vital Smoking.docx" and "tobacco_qualifier_to_pcornet_2.xlsx" under misc_docs in git hub. 
Initial feedback was that this looked to be a viable solution.
##Homework##
Review don's two documents, ask questions if necessary, be ready at the next meeting to say yes if you believe this is a workable solution or no if you find errors in the logic or cases that cannot be handled.
Meeting Notes June 30 2016
=============================================================================================================
We have agreed to a solution for how to record tobacco use in OMOP and to translate the values from OMOP to tobacco related values in the PCORnet vital table. It remains for Don to write up this solution and add it to 'ETL from OMOP CDM v5 to PCORnet CDM v3.doc'.

##Homework##
Review the Lab_Result_CM section in 'ETL from OMOP CDM v5 to PCORnet CDM v3.doc' available at https://github.com/don-torok/OMOPv5-to-PCORnetv3/blob/master/OMOP5_to_PCORnet3/ETL%20from%20OMOP%20CDM%20v5%20to%20PCORnet%20CDM%20v3.doc and be prepared to vet the section as is, or to add additional information that may be needed.

Meeting Note July 7, 2016
==========================================================================================
All agreed that little work was done during the July 4 holiday and that we should continue with the same homework assignment to review the Lab Result CM section to see if there are outstanding questions.  Don said that he has a mapping from UCUM Units to the unit representation recommended by PCORnet. A copy of this document is in github under misc_docs.

##Homework##
Review the Lab_Result_CM section in 'ETL from OMOP CDM v5 to PCORnet CDM v3.doc' available at https://github.com/don-torok/OMOPv5-to-PCORnetv3/blob/master/OMOP5_to_PCORnet3/ETL%20from%20OMOP%20CDM%20v5%20to%20PCORnet%20CDM%20v3.doc and be prepared to vet the section as is, or to add additional information that may be needed.

Meeting Notes July 21, 2016
===========================================================================================================
We had a number of people from Health Language, which is affiliated with Wolters Kluwer Health’s Clinical Solutions call into the meeting for a question and answer session on services that Health Language provides.  The entire meeting revolved around how Health Language could help a site to map their internal lab codes to LOINC identifiers. A site would provide as much information as possible describing lab tests that they order and a program that Health Languages wrote would map those attributes to a LOINC code and provide a level of confidence for the mapping.  Price was not discussed.

Depending on interest, we may have a follow-up meeting about natural language processing of clinical notes.

Lisa Schilling, lisa.schilling@ucdenver.edu, has offered to be our liaison with Health Language.

##Homework##
Determine if we would like a second meeting with Health Language to talk about using Natural Language Processing to extract clinical information from EHR notes and how this information might be brought into OMOP/PCORnet.

Health Language provided some insight on how to map to specific LOINC codes.  A quick google search identified the 6 axis (attributes) of LOINC's classification of Lab information.

1. Component (analyte): e.g., potassium, hemoglobin, hepatitis B antigen 
1. Property measured: e.g., a mass concentration, enzyme activity (catalytic rate) 
1. Timing: i.e., whether the observation applies to a moment in time or is an average or amount taken over a period of time, as is the case for a 24-h urine sodium concentration  
1. System: i.e., type of sample or organ examined: e.g., urine, blood, chest 
1. Scale: e.g., whether the measurement is quantitative (a true measurement), ordinal (a ranked set of options), nominal, or narrative (e.g., dictation results from x-rays)  
1. Method used to produce the observation, but only when different methods give clinically significant different results( an alternative definition: The process by which an observation value was obtained. Example methods include: weighing, use of a mass spectrometer, use of an ion sensitive electrode, and examination using a microscope.)

It would be interesting to see, with some additional googling, if someone could find a list of LOINC codes broken down by the 6 axis listed above.

Meeting Notes July 28, 2016
=====================================================================================================
Reviewed tasks necessary to update the OMOP Conventions and OMOP to PCORnet ETL documents to be consistent with OMOP CDMv5 and PCORnet v3.  Documents are in public git repository don-torok/OMOPv5-to-PCORnetv3.  The conventions document is under OMOP_conventions/CDRN Conventions for Populating OMOP CDM v5 for PCORnet v3.docx and the ETL document is under OMOP5_to_PCORnet3/ETL from OMOP CDM v5 to PCORnet CDM v3.docx.

Introduced new member Monica Ahuja from N.Y. CDRN

##Homework##
Lisa and Toan are going to get the "ETL from OMOP CDMv5 to PCORnet CDM v3" document from git and experiment with loading the document into google docs and making edits.  PCORnet changed the data-type for their date fields from text to date in version 3, Lisa will change to ETL doc to be consistent with the current date data-type.

Don will make changes to the Tobacco section of the conventions document to support our current scheme for recording tobacco related information in OMOP.

##Follow-up from last meeting##
Resources for mapping local labs to LOINC codes can be found at https://loinc.org/downloads.

Meeting Notes August 4, 2016
==========================================================================================================
From last weeks homework, Toan had loaded the OMOPv5 to PCORnet v3 document into google docs and we demonstrated that 1) the document did NOT loose existing formatting from word and 2) that multiple people can edit the document.  This is a vast improvement from maintaining the document in git where the file is treated as a binary file and can not merge changes. Given this new functionality, different items in the OMOP to PCORnet document that need to be corrected were assigned to people in the group.

As an aside, there was a discussion of how UC Denver is doing their ETL from a few different health providers EHR systems into a "pre-ETL" table and then using Rosita to ETL into OMOP CDMv4 tables.  Note, currently not assigning the target table as a function of the mapped to concept's domain or mapping type.  If there is sufficient interest in this approach to ETL we may use one of our meetings for a demo or set-up a demo outside of our standard meeting time.

##Homework##
Toan will move the OMOP conventions document from GitHub into google docs and grant edit privileges to whomever from the group is interested in sending their gmail addresses to Toan.  Others who may only want read can also request it from Toan.

Some items that are defined in a table at the beginning of the OMOP to PCORnet ETL doc as needed to be updated were assigned to various people in the group.  Edits will be done in google docs. Those given sections to update include Don, Rimma, Toan and Lisa. 

New comers Monika and Patrick and going to review the OMOP conventions and OMOP to PCORnet ETL docs to see if they make sense to someone that is new to the project.


















