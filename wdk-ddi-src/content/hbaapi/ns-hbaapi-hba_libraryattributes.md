---
UID: NS:hbaapi.HBA_LibraryAttributes
title: HBA_LibraryAttributes
author: windows-driver-content
description: The HBA_LibraryAttributes structure holds the library attributes.
old-location: storage\hba_libraryattributes.htm
old-project: storage
ms.assetid: 9dc03c5d-5e14-4399-b282-f0385a85a16c
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: "*PHBA_LIBRARYATTRIBUTES, HBA_LIBRARYATTRIBUTES, HBA_LIBRARYATTRIBUTES structure [Storage Devices], HBA_LibraryAttributes, HBA_LibraryAttributes structure [Storage Devices], PHBA_LIBRARYATTRIBUTES, PHBA_LIBRARYATTRIBUTES structure pointer [Storage Devices], hbaapi/HBA_LibraryAttributes, hbaapi/PHBA_LIBRARYATTRIBUTES, storage.hba_libraryattributes, structs-Fibre_1be227ba-622d-475f-811e-2d65de5cbaa8.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: hbaapi.h
req.include-header: Hbaapi.h
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	hbaapi.h
api_name:
-	HBA_LIBRARYATTRIBUTES
product: Windows
targetos: Windows
req.typenames: HBA_LIBRARYATTRIBUTES, *PHBA_LIBRARYATTRIBUTES
---

# HBA_LibraryAttributes structure


## -description


The HBA_LibraryAttributes structure holds the library attributes.


## -struct-fields




### -field final

Indicates, when <b>TRUE</b>, that the library implements the final and most recent draft of the T11 committee's <i>Fibre Channel HBA API</i> specification. When <b>FALSE</b> this member indicates that the library is not compliant with the most recent version of the specification. 


### -field LibPath

Contains the fully qualified path name of the library DLL file. 


### -field VName

Contains the name of the organization that developed the library code. 


### -field VVersion

Identifies the code revision of the library.


### -field build_date

Contains a structure of type tm that holds a timestamp that indicates when the library was built. The structure may contain the following members: 

<ul>
<li><b>tm_sec</b> Contains a value between 0 and 59 that indicates the number of seconds.</li>
<li><b>tm_min</b> Contains a value between 0 and 59 that indicates the number of minutes.</li>
<li><b>tm_hour</b> Contains a value between 0 and 23 that indicates the number of hours since midnight.</li>
<li><b>tm_mday</b> Contains a value between 1 and 31 that indicates the day of the month.</li>
<li><b>tm_mon</b> Contains a value between 0 and 11 that indicates the number of months since January.</li>
<li><b>tm_year</b> Indicates the number of years since 1900.</li>
<li><b>tm_wday</b> Contains a value between 0 and 6 that indicates the number of days since Sunday.</li>
<li><b>tm_yday</b> Contains a value between 0 and 365 that indicates the number of days since January 1.</li>
<li><b>tm_isdst</b> Indicates daylight savings time when TRUE and normal time when FALSE.</li>
</ul>
