# FDA_Applications_1998-2023
Looking at the FDA applications between years 1998 and 2023, span of 25 years. Data sourced from https://www.fda.gov/drugs/drug-approvals-and-databases/drugsfda-data-files 

Entity relationship diagram:

![Image](https://github.com/kilinandrea/FDA_Applications_1998-2023/blob/main/Drugs-FDA-ERD-Diagram-(Small).png)


*Drugs@FDA consists of 11 tables, I picked the following five:*

**ApplicationsDocsType_Lookup**

[ApplicationDocsType_Lookup_ID] [int] IDENTITY(1,1) NOT NULL

[ApplicationDocsType_Lookup_Description] [varchar] (200) NOT NULL


**ApplicationDocs**

[ApplicationDocsID] [int] IDENTITY(1,1) NOT NULL

[ApplicationDocsTypeID] [int] NOT NULL

[ApplNo] [char] (6) NOT NULL

[SubmissionType] [char] (10) NOT NULL

[SubmissionNo] [int] NOT NULL

[ApplicationDocsTitle] [varchar] (100) NULL

[ApplicationDocsURL] [varchar] (200) NULL

[ApplicationDocsDate] [datetime] NULL

**Applications**

[ApplNo] [char] (6) NOT NULL

[ApplType] [char] (5) NOT NULL

[ApplPublicNotes] [text] NULL

[SponsorName] [char] (500) NULL


**MarketingStatus**

[ApplNo] [char] (6) NOT NULL

[ProductNo] [char] (3) NOT NULL

[MarketingStatusID] [int] NOT NULL

**MarketingStatus_Lookup**

[MarketingStatusID] [int] IDENTITY(1,1) NOT NULL

[MarketingStatusDescription] [varchar] (200) NOT NULL

**Products**

[ApplNo] [char] (6) NOT NULL

[ProductNo] [char] (6) NOT NULL

[Form] [varchar] (255) NULL

[Strength] varchar] (240) NULL

[ReferenceDrug] [int] NULL

[DrugName] [varchar] (125) NULL

[ActiveIngredient] [varchar] (255) NULL

[ReferenceStandard] [int] NULL


