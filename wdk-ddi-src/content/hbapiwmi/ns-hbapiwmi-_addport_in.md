---
UID: NS:hbapiwmi._AddPort_IN
title: "_AddPort_IN"
author: windows-driver-content
description: The AddPort_IN structure is used by a WMI client to deliver the input parameter data of the AddPort WMI method to the HBA miniport driver.
old-location: storage\addport_in.htm
old-project: storage
ms.assetid: c9cdc0fc-e292-4142-a070-50a25a2a5673
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PAddPort_IN, AddPort_IN, AddPort_IN structure [Storage Devices], PAddPort_IN, PAddPort_IN structure pointer [Storage Devices], _AddPort_IN, hbapiwmi/AddPort_IN, hbapiwmi/PAddPort_IN, storage.addport_in, structs-Fibre_0f7b349b-048b-444c-b8ac-bdf63b00f998.xml"
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
-	AddPort_IN
product: Windows
targetos: Windows
req.typenames: AddPort_IN, *PAddPort_IN
---

# _AddPort_IN structure


## -description


The AddPort_IN structure is used by a WMI client to deliver the input parameter data of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff545022">AddPort</a> WMI method to the HBA miniport driver.


## -syntax


````
typedef struct _AddPort_IN {
  UCHAR PortWWN[8];
} AddPort_IN, *PAddPort_IN;
````


## -struct-fields




### -field PortWWN

Contains a worldwide name that indicates the port whose events are to be reported. 


## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff545022">AddPort</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20AddPort_IN structure%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

