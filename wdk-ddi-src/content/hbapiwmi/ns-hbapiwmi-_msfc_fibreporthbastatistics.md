---
UID: NS:hbapiwmi._MSFC_FibrePortHBAStatistics
title: "_MSFC_FibrePortHBAStatistics"
author: windows-driver-content
description: The MSFC_FibrePortHBAStatistics structure is used by an HBA miniport driver that is a WMI provider to report statistics related to a fibre channel port.
old-location: storage\msfc_fibreporthbastatistics.htm
old-project: storage
ms.assetid: 8b365e7a-6d52-417f-8c0b-78feac24602f
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ",  , *, *PMSFC_FibrePortHBAStatistics, ,, A, B, C, F, H, M, MSFC_FibrePortHBAStatistics, MSFC_FibrePortHBAStatistics structure [Storage Devices], P, PMSFC_FibrePortHBAStatistics, PMSFC_FibrePortHBAStatistics structure pointer [Storage Devices], S, _, _MSFC_FibrePortHBAStatistics, a, b, c, e, hbapiwmi/MSFC_FibrePortHBAStatistics, hbapiwmi/PMSFC_FibrePortHBAStatistics, i, o, r, s, storage.msfc_fibreporthbastatistics, structs-Fibre_d68738f2-ea37-420f-8356-51aa06362829.xml, t"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: hbapiwmi.h
req.include-header: Hbapiwmi.h
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	hbapiwmi.h
apiname:
-	MSFC_FibrePortHBAStatistics
product: Windows
targetos: Windows
req.typenames: MSFC_FibrePortHBAStatistics, *PMSFC_FibrePortHBAStatistics
---

# _MSFC_FibrePortHBAStatistics structure


## -description


The MSFC_FibrePortHBAStatistics structure is used by an HBA miniport driver that is a WMI provider to report statistics related to a fibre channel port.


## -syntax


````
typedef struct _MSFC_FibrePortHBAStatistics {
  ULONGLONG              UniquePortId;
  ULONG                  HBAStatus;
  MSFC_HBAPortStatistics Statistics;
} MSFC_FibrePortHBAStatistics, *PMSFC_FibrePortHBAStatistics;
````


## -struct-fields




### -field UniquePortId

Contains a unique identifier for the port. 


### -field HBAStatus

Contains the status of the operation. For a list of allowed values and their descriptions, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff557233">HBA_STATUS</a>. 


### -field Statistics

Contains a structure of type <a href="..\hbapiwmi\ns-hbapiwmi-_msfc_hbaportstatistics.md">MSFC_HBAPortStatistics</a> with statistical information about the port. 


## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff562505">MSFC_FibrePortHBAStatistics WMI Class</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20MSFC_FibrePortHBAStatistics structure%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

