---
UID: NF:portcls.PcNewServiceGroup
title: PcNewServiceGroup function
author: windows-driver-content
description: The PcNewServiceGroup function creates and initializes a service group.
old-location: audio\pcnewservicegroup.htm
old-project: audio
ms.assetid: 9fcc8cee-61a1-417c-9e69-5c658dab80b2
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: PcNewServiceGroup, audpc-routines_2164b9cd-1bb5-4e51-aa07-6ed9cb40e3fb.xml, audio.pcnewservicegroup, PcNewServiceGroup function [Audio Devices], portcls/PcNewServiceGroup
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: portcls.h
req.include-header: Portcls.h
req.target-type: Universal
req.target-min-winverclnt: The PortCls system driver implements the PcNewServiceGroup function in Microsoft Windows 98/Me and in Windows 2000 and later operating systems.
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
req.lib: Portcls.lib
req.dll: 
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Portcls.lib
-	Portcls.dll
apiname:
-	PcNewServiceGroup
product: Windows
targetos: Windows
req.typenames: PC_EXIT_LATENCY, *PPC_EXIT_LATENCY
---

# PcNewServiceGroup function


## -description


The <b>PcNewServiceGroup</b> function creates and initializes a service group.


## -syntax


````
NTSTATUS PcNewServiceGroup(
  _Out_    PSERVICEGROUP *OutServiceGroup,
  _In_opt_ PUNKNOWN      OuterUnknown
);
````


## -parameters




### -param OutServiceGroup [out]

Pointer to the service-group object created by this function. This parameter points to the caller-allocated pointer variable into which the function outputs the pointer to the <a href="..\portcls\nn-portcls-iservicegroup.md">IServiceGroup</a> object. Specify a valid, non-<b>NULL</b> pointer value for this parameter.


### -param OuterUnknown [in, optional]

Pointer to the <a href="https://msdn.microsoft.com/33f1d79a-33fc-4ce5-a372-e08bda378332">IUnknown</a> interface of an object that needs to aggregate the object. Unless aggregation is required, set this parameter to <b>NULL</b>.


## -returns


<b>PcNewServiceGroup</b> returns STATUS_SUCCESS if the call was successful. Otherwise, it returns an appropriate error code.



## -remarks


The <i>OutServiceGroup</i> and <i>OuterUnknown</i> parameters follow the <a href="https://msdn.microsoft.com/e6b19110-37e2-4d23-a528-6393c12ab650">reference-counting conventions for COM objects</a>.



## -see-also

<a href="..\portcls\nn-portcls-iservicegroup.md">IServiceGroup</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20PcNewServiceGroup function%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

