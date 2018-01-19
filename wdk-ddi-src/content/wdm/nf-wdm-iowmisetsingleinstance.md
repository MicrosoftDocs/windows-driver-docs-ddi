---
UID: NF:wdm.IoWMISetSingleInstance
title: IoWMISetSingleInstance function
author: windows-driver-content
description: The IoWMISetSingleInstance routine sets the values for properties within the data block instance that matches the specified WMI class and instance name.
old-location: kernel\iowmisetsingleinstance.htm
old-project: kernel
ms.assetid: 043b51cd-816f-414d-85b2-2573c42393e4
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: IoWMISetSingleInstance
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows XP and later versions of the Windows operating system.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IoWMISetSingleInstance
req.alt-loc: NtosKrnl.exe
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: <= APC_LEVEL
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# IoWMISetSingleInstance function



## -description
The <b>IoWMISetSingleInstance</b> routine sets the values for properties within the data block instance that matches the specified WMI class and instance name.



## -syntax

````
NTSTATUS IoWMISetSingleInstance(
  _In_ PVOID           DataBlockObject,
  _In_ PUNICODE_STRING InstanceName,
  _In_ ULONG           Version,
  _In_ ULONG           ValueBufferSize,
  _In_ PVOID           ValueBuffer
);
````


## -parameters

### -param DataBlockObject [in]

Pointer to a WMI data block object. The caller opens the data block object for the WMI class with the <a href="..\wdm\nf-wdm-iowmiopenblock.md">IoWMIOpenBlock</a> routine. The object must be opened with the WMIGUID_SET access right. 


### -param InstanceName [in]

Specifies the name of the instance of the data block. This value corresponds to the value of the <b>InstanceName</b> property for the block.


### -param Version [in]

Reserved for future use. Callers must set this parameter to zero.


### -param ValueBufferSize [in]

Specifies the size, in bytes, of the buffer passed in the <i>ValueBuffer</i> parameter.


### -param ValueBuffer [in]

Pointer to the buffer that contains the new values for the properties within the data block.


## -returns
The routine returns an NTSTATUS code. Possible return values include:
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>The operation succeeded. The values of the WMI data block instance properties are updated to the contents of the buffer pointed to by the <i>ValueBuffer</i> parameter.
<dl>
<dt><b>STATUS_WMI_GUID_NOT_FOUND</b></dt>
</dl>No drivers implement the WMI class.
<dl>
<dt><b>STATUS_WMI_INSTANCE_NOT_FOUND</b></dt>
</dl>No driver implements an instance of the WMI class with <b>InstanceName</b> property equal to the value specified in the <i>InstanceName</i> parameter.
<dl>
<dt><b>STATUS_WMI_READ_ONLY</b></dt>
</dl>All properties of the WMI class are read-only.
<dl>
<dt><b>STATUS_WMI_SET_FAILURE</b></dt>
</dl>The driver that implements the WMI data block instance is unable to update the instance.

 


## -remarks
<b>IoWMISetSingleInstance</b> determines which drivers might support the specified WMI class and instance name, and issues an <a href="https://msdn.microsoft.com/library/windows/hardware/ff550831">IRP_MN_CHANGE_SINGLE_INSTANCE</a> request to each such driver. The driver that exports the data block instance with matching <b>InstanceName</b> property updates its data block instance. Note that a data block might have both read-only and read/write properties. In this case, only the read/write properties will be updated and STATUS_SUCCESS is returned.

Drivers can also use the <a href="..\wdm\nf-wdm-iowmisetsingleitem.md">IoWMISetSingleItem</a> routine to update a single property within the class instance.


## -see-also
<dl>
<dt>
<a href="..\wdm\nf-wdm-iowmiopenblock.md">IoWMIOpenBlock</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-iowmiquerysingleinstance.md">IoWMIQuerySingleInstance</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-iowmisetsingleitem.md">IoWMISetSingleItem</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff550831">IRP_MN_CHANGE_SINGLE_INSTANCE</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20IoWMISetSingleInstance routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

