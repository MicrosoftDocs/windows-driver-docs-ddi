---
UID: NF:wdm.EtwWriteTransfer
title: EtwWriteTransfer function
author: windows-driver-content
description: The EtwWriteTransfer function marks an event that links two activities together; this type of event is referred to as a transfer event.
old-location: devtest\etwwritetransfer.htm
old-project: devtest
ms.assetid: 72a1c2f4-5f20-4c00-baf5-3d48fe27f48d
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: devtest.etwwritetransfer, EtwWriteTransfer function [Driver Development Tools], wdm/EtwWriteTransfer, EtwWriteTransfer, etw_km_210cf13d-0f54-4a51-b8f2-7d37b22d8eac.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	EtwWriteTransfer
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# EtwWriteTransfer function


## -description


The <b>EtwWriteTransfer</b> function marks an event that links two activities together; this type of event is referred to as a <i>transfer event</i>. A transfer event can contain the same user-defined data, the same fields, and is subject to the same rules as other events. 


## -syntax


````
NTSTATUS EtwWriteTransfer(
  _In_     REGHANDLE              RegHandle,
  _In_     PCEVENT_DESCRIPTOR     EventDescriptor,
  _In_opt_ LPCGUID                ActivityId,
  _In_opt_ LPCGUID                RelatedActivityId,
  _In_     ULONG                  UserDataCount,
  _In_opt_ PEVENT_DATA_DESCRIPTOR UserData
);
````


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

<a href="..\wdm\nf-wdm-etwwritestring.md">EtwWriteString</a>



<a href="..\wdm\nf-wdm-etwwrite.md">EtwWrite</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [devtest\devtest]:%20EtwWriteTransfer function%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

