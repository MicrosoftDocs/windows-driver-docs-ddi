---
UID: NS:ntddrilapitypes.RILUICCRECORDSTATUS
title: RILUICCRECORDSTATUS (ntddrilapitypes.h)
description: This structure represents RILUICCRECORDSTATUS.
old-location: netvista\riluiccrecordstatus.htm
tech.root: netvista
ms.assetid: 073fe700-ea6d-4d29-8751-66b27714f72d
ms.date: 02/16/2018
ms.keywords: "*LPRILUICCRECORDSTATUS, RILUICCRECORDSTATUS, RILUICCRECORDSTATUS structure [Network Drivers Starting with Windows Vista], netvista.riluiccrecordstatus, rilapitypes/RILUICCRECORDSTATUS"
f1_keywords:
 - "ntddrilapitypes/RILUICCRECORDSTATUS"
req.header: ntddrilapitypes.h
req.include-header: Ntddrilapitypes.h
req.target-type: Windows
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.ddi-compliance:
req.unicode-ansi:
req.idl:
req.max-support:
req.namespace:
req.assembly:
req.type-library:
req.lib:
req.dll:
req.irql:
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- rilapitypes.h
api_name:
- RILUICCRECORDSTATUS
product:
- Windows
targetos: Windows
req.typenames: RILUICCRECORDSTATUS, *LPRILUICCRECORDSTATUS
---

# RILUICCRECORDSTATUS structure


## -description


<div class="alert"><b>Warning</b>  The Cellular COM API is deprecated in Windows 10. This content is provided to support maintenance of OEM and mobile operator created Windows Phone 8.1 applications.</div><div> </div>This structure represents RILUICCRECORDSTATUS.


## -syntax


```cpp
struct RILUICCRECORDSTATUS {
  DWORD                 cbSize;
  DWORD                 dwParams;
  RILUICCRECORDTYPE     dwRecordType;
  DWORD                 dwItemCount;
  DWORD                 dwSize;
  RILUICCFILELOCKSTATUS fileLockStatus[MAXNUM_EFACCESSTYPES];
};
```


## -struct-fields




### -field cbSize

The size of the structure in bytes.


### -field dwParams

A bitwise combination of <a href="..\rilapitypes\ne-rilapitypes-riluiccrecordstatusparammask.md">RILUICCRECORDSTATUSPARAMMASK</a> enumeration values that indicates which members of the structure contain valid data. A member of the structure is valid if the corresponding bit flag is set.


### -field dwRecordType

Specifies the UICC file type, one of <a href="..\rilapitypes\ne-rilapitypes-riluiccrecordtype.md">RILUICCRECORDTYPE</a>.


### -field dwItemCount

Specifies the number of items in the UICC file.


### -field dwSize

Specifies the size of each item in bytes.


### -field fileLockStatus

An array of type <a href="..\rilapitypes\ns-rilapitypes-riluiccfilelockstatus.md">RILUICCFILELOCKSTATUS</a> that describes the access condition and a list of key references for each operation (READ, UPDATE, ACTIVATE, and DEACTIVATE in that order) on that file.


## -see-also

<a href="https://docs.microsoft.com/previous-versions/windows/hardware/cellular/dn946511(v=vs.85)">Cellular COM structures</a>



 

 


