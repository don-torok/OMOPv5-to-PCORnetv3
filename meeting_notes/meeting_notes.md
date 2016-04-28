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







