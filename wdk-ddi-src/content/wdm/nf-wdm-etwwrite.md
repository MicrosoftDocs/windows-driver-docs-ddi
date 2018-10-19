---
UID: NF:wdm.EtwWrite
title: EtwWrite function
author: windows-driver-content
description: The EtwWrite function is a tracing function for publishing events in your kernel-mode driver code.
old-location: devtest\etwwrite.htm
tech.root: devtest
ms.assetid: b9d4f6da-694d-4737-9cbe-3666e693c0a2
ms.date: 02/23/2018
ms.keywords: EtwWrite, EtwWrite function [Driver Development Tools], devtest.etwwrite, etw_km_af581b5c-6124-4bb0-8756-c4a0009e7a00.xml, wdm/EtwWrite
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	EtwWrite
product:
- Windows
targetos: Windows
req.typenames: 
---

# EtwWrite function


## -description


The <b>EtwWrite</b> function is a tracing function for publishing events in your kernel-mode driver code. 


## -parameters




### -param RegHandle [in]

A pointer to the event provider registration handle, which is returned by the <a href="https://msdn.microsoft.com/library/windows/hardware/ff545603">EtwRegister</a> function if the event provider registration is successful.


### -param EventDescriptor [in]

A pointer to the <a href="https://msdn.microsoft.com/907e6c38-5eaa-49da-9dc0-d055dcc69d1a">EVENT_DESCRIPTOR</a> structure. 


### -param ActivityId [in, optional]

The identifier that indicates the activity associated with the event. The <i>ActivityID</i> provides a way to group related events and is used in end-to-end tracing. 


### -param UserDataCount [in]

The number of EVENT_DATA_DESCRIPTOR structures in <i>UserData</i>.


### -param UserData [in, optional]

A pointer to the array of EVENT_DATA_DESCRIPTOR structures. 


## -returns



If the event was successfully published, <b>EtwWrite</b> returns STATUS_SUCCESS.

If the pointer to the event provider registration handle is invalid, <b>EtwWrite</b> returns STATUS_INVALID_HANDLE. The event provider must be registered before <b>EtwWrite</b> is called. <b>EtwWrite</b> can also return STATUS_INVALID_HANDLE if it is unable to log the event.



If the number of EVENT_DATA_DESCRIPTOR structures specified in <i>UserDataCount</i> is greater than the maximum allowed (128), <b>EtwWrite</b> returns STATUS_INVALID_PARAMETER.

If <i>ActivityID</i> is specified, but there is insufficient memory available to log the data associated with the event, <b>EtwWrite</b> returns STATUS_NO_MEMORY.



If the provider is not enabled for any session, <b>EtwWrite</b> returns STATUS_SUCCESS and the events are not logged.





Events can be lost for several reasons; for example, if the event rate is too high or if the event size is greater than the buffer size. In these cases, the <b>EventsLost</b> counter, a member of the EVENT_TRACE_PROPERTIES structure for the corresponding logger, is updated with the number of events that were not recorded.



<h3><a id="example"></a><a id="EXAMPLE"></a>Example</h3>
<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre> 
 //
 // Register the provider with ETW in DriverEntry
 // Unregister the provider in DriverUnload 
    //
 //  Build the EVENT_DATA_DESCRIPTOR structures using 
 //   the EventDataDescCreate macros 
 
 if (RegHandle != (REGHANDLE)NULL) {
 //
 // Log an Event with : DeviceNameLength
 //                      DeviceName
 //                      Status
 //
 
 EventDataDescCreate(&amp;EventDataDescriptor[0],
                            (PVOID)&amp;DeviceName.Length,
 sizeof(USHORT));
 

 EventDataDescCreate(&amp;EventDataDescriptor[1],
                            (PVOID)DeviceName.Buffer,
 DeviceName.Length);
 
 EventDataDescCreate(&amp;EventDataDescriptor[2],
                            (PVOID)&amp;Status,
 sizeof(ULONG));
 
 EtwWrite(RegHandle,            // Handle from EtwRegister
                 &amp;StartEvent,          // EventDescriptor
                 NULL,                 // Activity ID
                 3,                    // Number of data items
 EventDataDescriptor); // Array of data descriptors
    }              

//</pre>
</td>
</tr>
</table></span></div>



## -remarks



The <b>EtwWrite</b> function is the kernel-mode equivalent of the user-mode <b>EventWrite</b> function. To ensure that there is a consumer for the event you are publishing, you can precede the call to <b>EtwWrite</b> with a call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff545590">EtwEventEnabled</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff545595">EtwProviderEnabled</a>. 

Before you can call <b>EtwWrite</b> function to publish an event, you must register the provider with <b>EtwRegister</b>. No tracing calls should be made that fall outside of the code bounded by the <b>EtwRegister</b> and <b>EtwUnregister</b> functions. For the best performance, you can call the <b>EtwRegister</b> function in your <b>DriverEntry</b> routine and the <b>EtwUnregister</b> function in your <b>DriverUnload</b> routine.

If you are using the optional <i>UserData</i> parameter in the <b>EtwWrite</b> function to log additional event data, you can use the <b>EventDataDescCreate</b> macro to simplify the creation of the EVENT_DATA_DESCRIPTOR structures. The following example uses the <b>EventDataDescCreate</b> macro to initialize EVENT_DATA_DESCRIPTOR structures with  the name of the device and its status. The <b>EventDataDescCreate</b> macro stores pointers to the data (that is, it does not store copies of the data). The pointers must remain valid until the call to <b>EtwWrite</b> returns.

You can call <b>EtwWrite</b> at any IRQL. However, when IRQL is greater than APC_LEVEL, any data passed to the <b>EtwWrite</b>, <a href="https://msdn.microsoft.com/library/windows/hardware/dn144773">EtwWriteEx</a>, <b>EtwWriteString</b>, <b>EtwWriteTransfer</b> functions must not be pageable. That is, any kernel-mode routine that is running at IRQL greater than APC_LEVEL cannot access pageable memory.  Data passed to the <b>EtwWrite</b>, <b>EtwWriteEx</b>, <b>EtwWriteString</b>, and <b>EtwWriteTransfer</b> functions must reside in system-space memory, regardless of what the IRQL is.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff545590">EtwEventEnabled</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545595">EtwProviderEnabled</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545603">EtwRegister</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545613">EtwUnregister</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn144773">EtwWriteEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545637">EtwWriteString</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545642">EtwWriteTransfer</a>



<a href="http://go.microsoft.com/fwlink/p/?linkid=70404">EventDataDescCreate</a>
 

 

