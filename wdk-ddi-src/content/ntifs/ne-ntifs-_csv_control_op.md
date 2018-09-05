---
UID: NE:ntifs._CSV_CONTROL_OP
title: _CSV_CONTROL_OP
author: windows-driver-content
description: 
ms.assetid: a08a089b-44a0-45b7-98e3-8d82b3edef4b
ms.author: windowsdriverdev
ms.date: 
ms.topic: enum
ms.keywords: _CSV_CONTROL_OP, CSV_CONTROL_OP, *PCSV_CONTROL_OP, 
ms.prod: windows-hardware
ms.technology: windows-devices
req.header: ntifs.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.ddi-compliance:
req.max-support:
req.typenames: CSV_CONTROL_OP, *PCSV_CONTROL_OP
topictype: 
-	apiref
apitype: 
-	HeaderDef
apilocation: 
-	ntifs.h
apiname: 
-	_CSV_CONTROL_OP
product:
-	Windows
targetos: Windows
---

# _CSV_CONTROL_OP enumeration

## -description

Specifies the type of CSV control operation to use.


## -enum-fields

### -field CsvControlStartRedirectFile

Starts CSV file redirection.

### -field CsvControlStopRedirectFile 
Stops CSV file redirection.
### -field CsvControlQueryRedirectState 
Search for state redirection. When this value is specified, the CSV_QUERY_REDIRECT_STATE structure must also be used.
### -field CsvControlQueryFileRevision  
Search for file revision. When this value is specified, the CSV_QUERY_FILE_REVISION structure must also be used.
### -field CsvControlQueryMdsPath 
Search for MDS path. When this value is specified, the CSV_QUERY_MDS_PATH structure must also be used.
### -field CsvControlQueryFileRevisionFileId128 
TBD 
### -field CsvControlQueryVolumeRedirectState 
TBD 
### -field CsvControlEnableUSNRangeModificationTracking 
TBD 
### -field CsvControlMarkHandleLocalVolumeMount 
TBD 
### -field CsvControlUnmarkHandleLocalVolumeMount 
TBD 
### -field CsvControlGetCsvFsMdsPathV2 
TBD 

## -remarks

## -see-also

[File Management Enumerations](https://msdn.microsoft.com/library/windows/desktop/aa364231)

[CSV_CONTROL_PARAM](https://msdn.microsoft.com/library/windows/desktop/dn280466)

[CSV_QUERY_FILE_REVISION](https://msdn.microsoft.com/library/windows/desktop/dn280469)

[CSV_QUERY_MDS_PATH](https://msdn.microsoft.com/library/windows/desktop/dn280470) 

[CSV_QUERY_REDIRECT_STATE](https://msdn.microsoft.com/library/windows/desktop/dn280471)

[FSCTL_CSV_CONTROL](https://msdn.microsoft.com/library/windows/desktop/dn280516)