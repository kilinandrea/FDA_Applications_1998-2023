# FDA_Applications_1998-2023
Looking at the FDA applications between years 1998 and 2023, span of 25 years. Data sourced from https://www.fda.gov/drugs/drug-approvals-and-databases/drugsfda-data-files 

Entity relationship diagram:
!(Image)[https://github.com/kilinandrea/FDA_Applications_1998-2023/blob/main/Drugs-FDA-ERD-Diagram-(Small).png]

Drugs@FDA consists of 11 tables:

**ActionTypes_Lookup**

[ActionTypes_LookupID] [int] IDENTITY(1,1) NOT NULL
[ActionTypes_LookupDescription] [varchar](100) NOT NULL
[SupplCategoryLevel1Code] [varchar](100) NULL
[SupplCategoryLevel2Code] [varchar](100) NULL

**ApplicationDocs**

[ApplicationDocsID] [int] IDENTITY(1,1) NOT NULL
[ApplicationDocsTypeID] [int] NOT NULL
[ApplNo] [char](6) NOT NULL
[SubmissionType] [char](10) NOT NULL
[SubmissionNo] [int] NOT NULL
[ApplicationDocsTitle] [varchar](100) NULL
[ApplicationDocsURL] [varchar](200) NULL
[ApplicationDocsDate] [datetime] NULL

**Applications**

[ApplNo] [char](6) NOT NULL
[ApplType] [char](5) NOT NULL
[ApplPublicNotes] [text] NULL
[SponsorName] [char](500) NULL

**ApplicationsDocsType_Lookup**

[ApplicationDocsType_Lookup_ID] [int] IDENTITY(1,1) NOT NULL
ApplicationDocsType_Lookup_Description] [varchar](200) NOT NULL

**MarketingStatus**

[ApplNo] [char](6) NOT NULL,
[ProductNo] [char](3) NOT NULL,
[MarketingStatusID] [int] NOT NULL

**MarketingStatus_Lookup**

[MarketingStatusID] [int] IDENTITY(1,1) NOT NULL
[MarketingStatusDescription] [varchar](200) NOT NULL

**Products**

[ApplNo] [char](6) NOT NULL
[ProductNo] [char](6) NOT NULL
[Form] [varchar](255) NULL
[Strength] varchar](240) NULL
[ReferenceDrug] [int] NULL
[DrugName] [varchar](125) NULL
[ActiveIngredient] [varchar](255) NULL
[ReferenceStandard] [int] NULL

**SubmissionClass_Lookup**

[SubmissionClassCodeID] [int] IDENTITY(1,1) NOT NULL
[SubmissionClassCode] [varchar](50) NOT NULL
[SubmissionClassCodeDescription] [varchar](500) NULL

**SubmissionPropertyType**

[ApplNo] [char](6) NOT NULL
[SubmissionType] [char](10) NOT NULL
[SubmissionNo] [int] NOT NULL
[SubmissionPropertyTypeCode] [varchar](50) NOT NULL (Orphan or NULL)
SubmissionPropertyTypeID [int] NOT NULL

**Submissions**

[ApplNo] [char](6) NOT NULL
[SubmissionClassCodeID] [int] NULL
[SubmissionType] [char](10) NOT NULL
[SubmissionNo] [int] NOT NULL
[SubmissionStatus] [char](2) NULL
[SubmissionStatusDate] [datetime] NULL
[SubmissionsPublicNotes] [text] NULL
[ReviewPriority] [varchar](20) (Standard, Priority, NULL)
 
**TE**

[ApplNo] [char](6) NOT NULL
[ProductNo] [char](3) NOT NULL
[MarketingStatusID] [int] NOT NULL
[TECode] [varchar](100) NOT NULL
