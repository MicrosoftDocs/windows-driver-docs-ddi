---
UID: NF:wdm.IoWMIQuerySingleInstance
title: IoWMIQuerySingleInstance function
author: windows-driver-content
description: The IoWMIQuerySingleInstance routine returns the specified instance of a WMI data block.
old-location: kernel\iowmiquerysingleinstance.htm
old-project: kernel
ms.assetid: 742535da-4726-4320-88ec-f6752ad02fb3
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: IoWMIQuerySingleInstance
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
req.alt-api: IoWMIQuerySingleInstance
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

# IoWMIQuerySingleInstance function



## -description
The <b>IoWMIQuerySingleInstance</b> routine returns the specified instance of a WMI data block.



## -syntax

````
NTSTATUS IoWMIQuerySingleInstance(
  _In_      PVOID           DataBlockObject,
  _In_      PUNICODE_STRING InstanceName,
  _Inout_   ULONG           *InOutBufferSize,
  _Out_opt_ PVOID           OutBuffer
);
````


## -parameters

### -param DataBlockObject [in]

Pointer to a WMI data block object. The caller opens the data block object for the WMI class with the <a href="..\wdm\nf-wdm-iowmiopenblock.md">IoWMIOpenBlock</a> routine. The object must be opened with the WMIGUID_QUERY access right.


### -param InstanceName [in]

Specifies the name of the instance of the data block. This value corresponds to the value of the <b>InstanceName</b> property for the block.


### -param InOutBufferSize [in, out]

Pointer to a memory location that specifies the size of the buffer passed in the <i>OutBuffer</i> parameter. If the routine succeeds, it updates the memory location to specify the number of bytes actually stored in <i>OutBuffer</i>. If the routine fails with status code of STATUS_BUFFER_TOO_SMALL, it returns the number of bytes required to return the data.


### -param OutBuffer [out, optional]

Pointer to the buffer where the routine returns the WMI data. The routine returns a variable-sized <a href="..\wmistr\ns-wmistr-tagwnode_single_instance.md">WNODE_SINGLE_INSTANCE</a> structure. <i>OutBuffer</i> must point to a buffer allocated from nonpaged pool.


## -returns
The routine returns an NTSTATUS code. Possible return values include:
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>The operation succeeded. The routine returns the WMI data in the buffer pointed to by the <i>OutBuffer</i> parameter. The routine also returns the size, in bytes, of the returned data in the memory location pointed to by the <i>InOutBufferSize</i> parameter.
<dl>
<dt><b>STATUS_WMI_GUID_NOT_FOUND</b></dt>
</dl>No drivers implement the specified WMI class.
<dl>
<dt><b>STATUS_WMI_INSTANCE_NOT_FOUND</b></dt>
</dl>No driver implements an instance of the WMI class with <b>InstanceName</b> property equal to the value specified in the <i>InstanceName</i> parameter.
<dl>
<dt><b>STATUS_BUFFER_TOO_SMALL</b></dt>
</dl>The buffer passed by the caller in the <i>OutBuffer</i> parameter is too small. The routine returns the required buffer size in the memory location pointed to by the <i>InOutBufferSize</i> parameter.

 


## -remarks
<b>IoWMIQuerySingleInstance</b> determines which drivers might support the specified WMI class with the specified instance name, and issues an <a href="https://msdn.microsoft.com/library/windows/hardware/ff551718">IRP_MN_QUERY_SINGLE_INSTANCE</a> request to each such driver. The driver that exports the data block instance with matching <b>InstanceName</b> property returns the appropriate data.

To query for multiple WMI classes and instance names, use the <a href="..\wdm\nf-wdm-iowmiquerysingleinstancemultiple.md">IoWMIQuerySingleInstanceMultiple</a> routine. Drivers can use the <a href="..\wdm\nf-wdm-iowmisetsingleinstance.md">IoWMISetSingleInstance</a> routine to update the class instance. 


## -see-also
<dl>
<dt>
<a href="..\wdm\nf-wdm-iowmiopenblock.md">IoWMIOpenBlock</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-iowmiquerysingleinstancemultiple.md">IoWMIQuerySingleInstanceMultiple</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-iowmisetsingleinstance.md">IoWMISetSingleInstance</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff551718">IRP_MN_QUERY_SINGLE_INSTANCE</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20IoWMIQuerySingleInstance routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

