---
UID: NS:hbapiwmi._SetFC3MgmtInfo_OUT
title: "_SetFC3MgmtInfo_OUT"
author: windows-driver-content
description: The SetFC3MgmtInfo_OUT structure is used to report the output parameter data of the SetFC3MgmtInfo WMI method to the WMI client.
old-location: storage\setfc3mgmtinfo_out.htm
old-project: storage
ms.assetid: 00e6eb1a-3302-46ac-b859-9c22ad6cee22
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: PSetFC3MgmtInfo_OUT structure pointer [Storage Devices], hbapiwmi/PSetFC3MgmtInfo_OUT, PSetFC3MgmtInfo_OUT, SetFC3MgmtInfo_OUT, *PSetFC3MgmtInfo_OUT, structs-Fibre_86907ae9-a0a0-4836-a822-d07cd2adfdb0.xml, _SetFC3MgmtInfo_OUT, storage.setfc3mgmtinfo_out, SetFC3MgmtInfo_OUT structure [Storage Devices], hbapiwmi/SetFC3MgmtInfo_OUT
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
-	SetFC3MgmtInfo_OUT
product: Windows
targetos: Windows
req.typenames: SetFC3MgmtInfo_OUT, *PSetFC3MgmtInfo_OUT
---

# _SetFC3MgmtInfo_OUT structure


## -description


The SetFC3MgmtInfo_OUT structure is used to report the output parameter data of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff565657">SetFC3MgmtInfo</a> WMI method to the WMI client.


## -syntax


````
typedef struct _SetFC3MgmtInfo_OUT {
  ULONG HBAStatus;
} SetFC3MgmtInfo_OUT, *PSetFC3MgmtInfo_OUT;
````


## -struct-fields




#### - HBAStatus

Contains the status of the operation. For a list of allowed values and their descriptions, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff557233">HBA_STATUS</a>. 


## -remarks


The WMI tool suite generates a declaration of the SetFC3MgmtInfo_OUT structure in <i>Hbapiwmi.h </i>when it compiles the <a href="https://msdn.microsoft.com/library/windows/hardware/ff562506">MSFC_HBAAdapterMethods WMI Class</a>.



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff565657">SetFC3MgmtInfo</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20SetFC3MgmtInfo_OUT structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

