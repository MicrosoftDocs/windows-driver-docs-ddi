---
UID: NF:wdm.IoWMISetSingleItem
title: IoWMISetSingleItem function (wdm.h)
description: The IoWMISetSingleItem routine sets a single property in the data block instance that matches the specified WMI class and instance name.
old-location: kernel\iowmisetsingleitem.htm
tech.root: kernel
ms.assetid: 73c6ddaa-f090-430a-86b5-61b33cb8ffc8
ms.date: 04/30/2018
keywords: ["IoWMISetSingleItem function"]
ms.keywords: IoWMISetSingleItem, IoWMISetSingleItem routine [Kernel-Mode Driver Architecture], k104_cc50cf7d-a35a-42d6-86e2-4fb6a6183323.xml, kernel.iowmisetsingleitem, wdm/IoWMISetSingleItem
f1_keywords:
 - "wdm/IoWMISetSingleItem"
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows XP and later versions of the Windows operating system.
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
req.irql: <= APC_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- IoWMISetSingleItem
product:
- Windows
targetos: Windows
req.typenames: 
---

# IoWMISetSingleItem function


## -description


The <b>IoWMISetSingleItem</b> routine sets a single property in the data block instance that matches the specified WMI class and instance name. 


## -parameters




### -param DataBlockObject [in]

Pointer to a WMI data block object. The caller opens the data block object for the WMI class with the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-iowmiopenblock">IoWMIOpenBlock</a> routine. The object must be opened with the WMIGUID_SET access right. 


### -param InstanceName [in]

Specifies the name of the instance of the data block. This value corresponds to the value of the <b>InstanceName</b> property for the block. 


### -param DataItemId [in]

Specifies the data item ID for the property to be set. The value of this parameter corresponds to the value declared in the <b>WmiDataId</b> qualifier for the property.


### -param Version [in]

Reserved for future use. Callers must set this parameter to zero.


### -param ValueBufferSize [in]

Specifies the size, in bytes, of the buffer passed in the <i>ValueBuffer</i> parameter.


### -param ValueBuffer [in]

Pointer to the buffer that contains the new value for the property specified by the <i>DataItemId</i> parameter. 


## -returns



The routine returns an NTSTATUS code. Possible return values include:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The operation succeeded. The value of the property within WMI data block instance is updated to the contents of the buffer pointed to by the <i>ValueBuffer</i> parameter.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_WMI_GUID_NOT_FOUND</b></dt>
</dl>
</td>
<td width="60%">
No drivers implement the WMI class.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_WMI_INSTANCE_NOT_FOUND</b></dt>
</dl>
</td>
<td width="60%">
No driver implements an instance of the WMI data block with <b>InstanceName</b> property equal to the value specified in the <i>InstanceName</i> parameter.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_WMI_ITEMID_NOT_FOUND</b></dt>
</dl>
</td>
<td width="60%">
The WMI class does not contain a property with data item ID equal to the value of <i>DataItemId</i>.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_WMI_READ_ONLY</b></dt>
</dl>
</td>
<td width="60%">
The data item ID in the data block is read-only.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_WMI_SET_FAILURE</b></dt>
</dl>
</td>
<td width="60%">
The driver that implements the WMI data block instance is unable to update the property specified by <i>DataItemId</i>.

</td>
</tr>
</table>
 




## -remarks



<b>IoWMISetSingleItem</b> determines which drivers might support the specified WMI class and instance name. It issues an <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mn-change-single-item">IRP_MN_CHANGE_SINGLE_ITEM</a> request to each such driver. The driver that exports the data block instance with matching <b>InstanceName</b> property updates the specified property in the data block instance.

Drivers can also use <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-iowmisetsingleinstance">IoWMISetSingleInstance</a> to update every property of the WMI class instance simultaneously.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mn-change-single-item">IRP_MN_CHANGE_SINGLE_ITEM</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-iowmiopenblock">IoWMIOpenBlock</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-iowmiquerysingleinstance">IoWMIQuerySingleInstance</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-iowmisetsingleinstance">IoWMISetSingleInstance</a>
 

 

