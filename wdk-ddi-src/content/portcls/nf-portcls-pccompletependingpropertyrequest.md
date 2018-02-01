---
UID: NF:portcls.PcCompletePendingPropertyRequest
title: PcCompletePendingPropertyRequest function
author: windows-driver-content
description: The PcCompletePendingPropertyRequest function is called to complete a pending property request.
old-location: audio\pccompletependingpropertyrequest.htm
old-project: audio
ms.assetid: a4b59403-9a2f-4857-947b-dff8e3ea079c
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: audpc-routines_934503ea-325f-4e57-ba45-e8834a64cefa.xml, PcCompletePendingPropertyRequest function [Audio Devices], portcls/PcCompletePendingPropertyRequest, PcCompletePendingPropertyRequest, audio.pccompletependingpropertyrequest
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: portcls.h
req.include-header: Portcls.h
req.target-type: Universal
req.target-min-winverclnt: The PortCls system driver implements the PcCompletePendingPropertyRequest function in Microsoft Windows 98/Me and in Windows 2000 and later operating systems.
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
req.irql: "<=DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Portcls.lib
-	Portcls.dll
apiname:
-	PcCompletePendingPropertyRequest
product: Windows
targetos: Windows
req.typenames: "*PPC_EXIT_LATENCY, PC_EXIT_LATENCY"
---

# PcCompletePendingPropertyRequest function


## -description


The <b>PcCompletePendingPropertyRequest</b> function is called to complete a pending property request.


## -syntax


````
NTSTATUS PcCompletePendingPropertyRequest(
  _In_ PPCPROPERTY_REQUEST PropertyRequest,
  _In_ NTSTATUS            NtStatus
);
````


## -parameters




### -param PropertyRequest [in]

Pointer to the property request that was passed to the property handler. The request is a structure of type <a href="..\portcls\ns-portcls-_pcproperty_request.md">PCPROPERTY_REQUEST</a>.


### -param NtStatus [in]

Specifies the completion status of the request. See the list of NTSTATUS values defined in header file ntstatus.h.


## -returns


<b>PcCompletePendingPropertyRequest</b> returns STATUS_SUCCESS if the call was successful. Otherwise, it returns an appropriate error code.



## -remarks


If a miniport driver returns STATUS_PENDING from a property handler, it is obliged to keep a pointer to the property-request structure and to complete the request at some later time by calling this function.

The driver should call <b>PcCompletePendingPropertyRequest</b> only when the request is no longer pending. Never call this function with an <i>NtStatus</i> value of STATUS_PENDING. 



## -see-also

<a href="..\wdm\nf-wdm-iocompleterequest.md">IoCompleteRequest</a>

<a href="..\portcls\ns-portcls-_pcproperty_request.md">PCPROPERTY_REQUEST</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20PcCompletePendingPropertyRequest function%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

