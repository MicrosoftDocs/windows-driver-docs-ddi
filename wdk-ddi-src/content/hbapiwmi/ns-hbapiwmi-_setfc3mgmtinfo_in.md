---
UID: NS:hbapiwmi._SetFC3MgmtInfo_IN
title: "_SetFC3MgmtInfo_IN"
author: windows-driver-content
description: The SetFC3MgmtInfo_IN structure is used to deliver input parameter data to the SetFC3MgmtInfo WMI method.
old-location: storage\setfc3mgmtinfo_in.htm
old-project: storage
ms.assetid: 2ad51d73-67f3-4ce0-b7e1-6bdc1b7e3b0c
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: "*PSetFC3MgmtInfo_IN, PSetFC3MgmtInfo_IN, PSetFC3MgmtInfo_IN structure pointer [Storage Devices], SetFC3MgmtInfo_IN, SetFC3MgmtInfo_IN structure [Storage Devices], _SetFC3MgmtInfo_IN, hbapiwmi/PSetFC3MgmtInfo_IN, hbapiwmi/SetFC3MgmtInfo_IN, storage.setfc3mgmtinfo_in, structs-Fibre_d4b69005-dc94-411f-810a-6767699e0b11.xml"
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	hbapiwmi.h
api_name:
-	SetFC3MgmtInfo_IN
product: Windows
targetos: Windows
req.typenames: SetFC3MgmtInfo_IN, *PSetFC3MgmtInfo_IN
---

# _SetFC3MgmtInfo_IN structure


## -description


The SetFC3MgmtInfo_IN structure is used to deliver input parameter data to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff565657">SetFC3MgmtInfo</a> WMI method.


## -syntax


````
typedef struct _SetFC3MgmtInfo_IN {
  HBAFC3MgmtInfo MgmtInfo;
} SetFC3MgmtInfo_IN, *PSetFC3MgmtInfo_IN;
````


## -struct-fields




### -field MgmtInfo

Contains a structure of type <a href="..\hbapiwmi\ns-hbapiwmi-_hbafc3mgmtinfo.md">HBAFC3MgmtInfo</a> that holds FC3 management information that will be used to configure the fibre channel adapter. 


## -remarks



The WMI tool suite generates a declaration of the SetFC3MgmtInfo_IN structure in <i>Hbapiwmi.h </i>when it compiles the <a href="https://msdn.microsoft.com/library/windows/hardware/ff562506">MSFC_HBAAdapterMethods WMI Class</a>.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff565657">SetFC3MgmtInfo</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20SetFC3MgmtInfo_IN structure%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

