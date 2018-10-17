---
UID: NF:wdm.EtwWriteEx
title: EtwWriteEx function
author: windows-driver-content
description: The EtwWriteEx function is a tracing function for publishing events that support filtering in your kernel-mode driver code.
old-location: devtest\etwwriteex.htm
tech.root: devtest
ms.assetid: E2EF929A-61EB-412B-B8E8-D51FD6944B1D
ms.date: 2/23/2018
ms.keywords: EtwWriteEx, EtwWriteEx function [Driver Development Tools], devtest.etwwriteex, wdm/EtwWriteEx
ms.topic: function
req.header: wdm.h
req.include-header: 
req.target-type: Universal
req.target-min-winverclnt: Windows 7
req.target-min-winversvr: Windows Server 2008 R2
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	EtwWriteEx
product:
- Windows
targetos: Windows
req.typenames: 
---

# EtwWriteEx function


## -description


The <b>EtwWriteEx</b> function is a tracing function for publishing events that support filtering in your kernel-mode driver code. 


## -parameters




### -param RegHandle [in]

A pointer to the event provider registration handle, which is returned by the <a href="https://msdn.microsoft.com/library/windows/hardware/ff545603">EtwRegister</a> function if the event provider registration is successful.


### -param EventDescriptor [in]

A pointer to the <a href="https://msdn.microsoft.com/907e6c38-5eaa-49da-9dc0-d055dcc69d1a">EVENT_DESCRIPTOR</a> structure. 


### -param Filter [in]

The instance identifiers that identify the session to which the event will not written. That is, the value is a mask of sessions which should be excluded from logging (filtered out). Use a bitwise OR to specify multiple identifiers. Set to zero if you do not support filters or if the event is being written to all sessions (no filters failed). For information on getting the identifier for a session, see the <i>FilterData</i> parameter of your <a href="https://msdn.microsoft.com/5953a3ae-b130-42fd-9dc8-974d15c6dfc5">EtwEnableCallback</a> callback.  


### -param Flags [in]

Reserved.  Must be  zero (0). 


### -param ActivityId [in, optional]

The identifier that indicates the activity associated with the event. The <i>ActivityID</i> provides a way to group related events and is used in end-to-end tracing.  If NULL, ETW gets the identifier from the thread local storage. For details on getting this identifier, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff545578">EtwActivityIdControl</a>.


### -param RelatedActivityId [in, optional]

Activity identifier from the previous component. Use this parameter to link your component's events to the previous component's events. To get the activity identifier that was set for the previous component, see the descriptions for the <i>ControlCode</i> parameter of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff545578">EtwActivityIdControl</a> function.


### -param UserDataCount [in]

Number of EVENT_DATA_DESCRIPTOR structures in <i>UserData</i>. The maximum number is 128.


### -param UserData [in, optional]

A pointer to the array of EVENT_DATA_DESCRIPTOR structures. Set this parameter to NULL if <i>UserDataCount</i> is zero. The data must be in the order specified in the manifest.


## -returns



Returns ERROR_SUCCESS if successful or one of the following values on error.




## -remarks



The <b>EtwWriteEx</b> function is the kernel-mode equivalent of the user-mode <a href="https://msdn.microsoft.com/00b907cb-45cd-48c7-bea4-4d8a39b4fa24">EventWriteEx</a> function. Event data written with this function requires a manifest. The manifest is embedded in the provider, so the provider must be available for a consumer to consume the data. To ensure that there is a consumer for the event you are publishing, you can precede the call to <b>EtwWrite</b> with a call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff545590">EtwEventEnabled</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff545595">EtwProviderEnabled</a>. 

Use the <i>ActivityId</i> and <i>RelatedActivityId</i> parameters when you want to relate events in different components in an end-to-end tracing scenario. For example, components A, B, and C perform work on a related activity and want to link their events so that a consumer can consume all the events related to that activity. 

You can call <b>EtwWriteEx</b> at any IRQL. However, when IRQL is greater than APC_LEVEL, any data passed to the <b>EtwWrite</b>, <b>EtwWriteEx</b>, <b>EtwWriteString</b>, <b>EtwWriteTransfer</b> functions must not be pageable. That is, any kernel-mode routine that is running at IRQL greater than APC_LEVEL cannot access pageable memory.  Data passed to the <b>EtwWrite</b>, <b>EtwWriteEx</b>, <b>EtwWriteString</b>,  and <b>EtwWriteTransfer</b> functions must reside in system-space memory, regardless of what the IRQL is.






## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff545627">EtwWrite</a>



<a href="https://msdn.microsoft.com/93070eb7-c167-4419-abff-e861877dad07">EventWrite</a>



<a href="https://msdn.microsoft.com/00b907cb-45cd-48c7-bea4-4d8a39b4fa24">EventWriteEx</a>
 

 

