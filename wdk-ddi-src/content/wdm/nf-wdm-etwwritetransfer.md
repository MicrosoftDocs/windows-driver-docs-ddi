---
UID: NF:wdm.EtwWriteTransfer
title: EtwWriteTransfer function (wdm.h)
description: The EtwWriteTransfer function marks an event that links two activities together; this type of event is referred to as a transfer event.
old-location: devtest\etwwritetransfer.htm
tech.root: devtest
ms.assetid: 72a1c2f4-5f20-4c00-baf5-3d48fe27f48d
ms.date: 02/23/2018
keywords: ["EtwWriteTransfer function"]
ms.keywords: EtwWriteTransfer, EtwWriteTransfer function [Driver Development Tools], devtest.etwwritetransfer, etw_km_210cf13d-0f54-4a51-b8f2-7d37b22d8eac.xml, wdm/EtwWriteTransfer
f1_keywords:
 - "wdm/EtwWriteTransfer"
 - "EtwWriteTransfer"
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows Vista and later versions of Windows.
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: Any level (See Comments section.)
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- EtwWriteTransfer
targetos: Windows
req.typenames: 
---

# EtwWriteTransfer function


## -description


The <b>EtwWriteTransfer</b> function marks an event that links two activities together; this type of event is referred to as a <i>transfer event</i>. A transfer event can contain the same user-defined data, the same fields, and is subject to the same rules as other events. 


## -parameters




### -param RegHandle [in]

A pointer to the event provider registration handle, which is returned by the <b>EtwRegister</b> function if the event provider registration is successful.


### -param EventDescriptor [in]

A pointer to the EVENT_DESCRIPTOR structure. 


### -param ActivityId [in, optional]

The identifier that indicates the activity associated with the event. The <i>ActivityId</i> provides a way to group related events and is used in end-to-end tracing. This identifier is optional and can be <b>NULL</b>.


### -param RelatedActivityId [in, optional]

The identifier that indicates related activity associated with the event. The <i>RelatedActivityID</i> provides a way to group related events and is used in end-to-end tracing. 


### -param UserDataCount [in]

The number of elements in an array of EVENT_DATA_DESCRIPTOR structures. 


### -param UserData [in, optional]

The pointer to the first element in an array of EVENT_DATA_DESCRIPTOR structures. 


## -returns



<b>EtwWriteTransfer</b> returns STATUS_SUCCESS if the event was successfully published.




## -remarks



You can call <b>EtwWriteTransfer</b> at any IRQL. However, when IRQL is greater than APC_LEVEL, any data passed to the <b>EtwWrite</b>, <b>EtwWriteString</b>, <b>EtwWriteTransfer</b> functions must not be pageable. That is, any kernel-mode routine that is running at IRQL greater than APC_LEVEL cannot access pageable memory. Data passed to the <b>EtwWrite</b>, <b>EtwWriteString</b>, <b>EtwWriteTransfer</b> functions must reside in system-space memory, regardless of what the IRQL is.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-etwwrite">EtwWrite</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-etwwritestring">EtwWriteString</a>
 

 

