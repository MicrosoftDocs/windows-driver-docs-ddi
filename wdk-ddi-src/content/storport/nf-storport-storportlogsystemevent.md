---
UID: NF:storport.StorPortLogSystemEvent
title: StorPortLogSystemEvent function
author: windows-driver-content
description: The StorPortLogSystemEvent routine gives miniport drivers full access to the capabilities of the Windows kernel event facility, enabling miniport drivers to create event log entries that are truly useful in troubleshooting storage issues.
old-location: storage\storportlogsystemevent.htm
old-project: storage
ms.assetid: 720245ff-8c97-4b8d-8406-f6b712fa74c9
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: StorPortLogSystemEvent, StorPortLogSystemEvent routine [Storage Devices], storage.storportlogsystemevent, storport/StorPortLogSystemEvent, storprt_15a23037-a0e9-4768-ab20-80d6fe7d8a56.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: storport.h
req.include-header: Storport.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: StorPortIrql
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.exe
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	storport.h
api_name:
-	StorPortLogSystemEvent
product: Windows
targetos: Windows
req.typenames: STOR_SPINLOCK
req.product: Windows 10 or later.
---

# StorPortLogSystemEvent function


## -description


The StorPortLogSystemEvent routine gives miniport drivers full access to the capabilities of the Windows kernel event facility, enabling miniport drivers to create event log entries that are truly useful in troubleshooting storage issues. It provides a better alternative to the existing miniport driver event logging function, <a href="..\storport\nf-storport-storportlogerror.md">StorPortLogError</a>.


## -syntax


````
ULONG StorPortLogSystemEvent(
  _In_    PVOID                   HwDeviceExtension,
  _Inout_ PSTOR_LOG_EVENT_DETAILS LogDetails,
  _Inout_ PULONG                  MaximumSize
);
````


## -parameters




### -param HwDeviceExtension [in]

A pointer to the hardware device extension. This is a per HBA storage area that the port driver allocates and initializes on behalf of the miniport driver. Miniport drivers usually store HBA-specific information in this extension, such as the state of the HBA and the mapped access ranges for the HBA. This area is available to the miniport immediately after the miniport driver calls <a href="..\storport\nf-storport-storportinitialize.md">StorPortInitialize</a>. The port driver frees this memory when it removes the device.


### -param LogDetails [in, out]

Information to appear in the system event log entry.


### -param MaximumSize [in, out]

Variable to receive maximum combined size of miniport's dump data and strings. Only returned if the function fails and returns a STOR_STATUS_INVALID_BUFFER_SIZE value. This parameter is optional.


## -returns



<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STOR_STATUS_NOT_IMPLEMENTED</b></dt>
</dl>
</td>
<td width="60%">
This function is not implemented on the active operating system.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STOR_STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
An invalid parameter was passed in.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STOR_STATUS_INVALID_IRQL</b></dt>
</dl>
</td>
<td width="60%">
The call was made at IRQL &gt; DISPATCH_LEVEL.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STOR_STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
There were insufficient system resources to complete the request.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STOR_STATUS_UNSUPPORTED_VERSION:</b></dt>
</dl>
</td>
<td width="60%">
An unsupported (for example, more current) version of the STOR_LOG_EVENT_DETAILS structure was specified. When this is returned, LogDetails-&gt;InterfaceRevision is set to the latest supported version.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STOR_STATUS_INVALID_BUFFER_SIZE</b></dt>
</dl>
</td>
<td width="60%">
The buffers passed to the function were too large. When this value is returned, MaximumSize is set to the maximum combined size of the miniport's dump data and strings.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STOR_STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The log operation completed successfully.

</td>
</tr>
</table>
 




## -remarks



To understand how you may use custom error codes to best advantage, see  <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/storage/storport-event-log-extensions">Storport Error Log Extensions</a>. The StorPortLogSystemEvent routine must be called at IRQL &lt;= DISPATCH_LEVEL. If you pass in a more recent version of STOR_LOG_EVENT_DETAILS than  that supported by this build, this function changes the InterfaceRevision field to the latest supported version and returns STOR_STATUS_UNSUPPORTED_VERSION. The InterfaceRevision field of STOR_LOG_EVENT_DETAILS is a 32-bit value. However, only the three most-significant bytes are used for validation. The low byte is reserved to distinguish between compatible, minor variations of a particular version. For instance, a revision 0x00000101 structure is compatible with a Storport that implements revision 0x00000100 of the interface, although it is possible that some minor, noncritical functionality may be lost. If you specify a combined size of dump data and strings that exceeds the maximum allowed event log entry size, the integer pointed to by MaximumSize is set to the maximum allowed size of miniport dump data and strings, and STOR_INVALID_BUFFER_SIZE is returned. Although this function accepts ULONG values for the path, target, and LUN address specifiers, the values are truncated to UCHAR values because Storport internally only supports 8-bit values for these specifiers. 




## -see-also

<a href="..\storport\nf-storport-storportlogerror.md">StorPortLogError</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20StorPortLogSystemEvent routine%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

