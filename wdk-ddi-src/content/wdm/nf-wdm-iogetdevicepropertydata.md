---
UID: NF:wdm.IoGetDevicePropertyData
title: IoGetDevicePropertyData function (wdm.h)
description: The IoGetDevicePropertyData routine retrieves the current setting for a device property.
old-location: kernel\iogetdevicepropertydata.htm
tech.root: kernel
ms.assetid: 3ca026b8-abed-409c-8be4-01553cfadca3
ms.date: 04/30/2018
keywords: ["IoGetDevicePropertyData function"]
ms.keywords: IoGetDevicePropertyData, IoGetDevicePropertyData routine [Kernel-Mode Driver Architecture], k104_85cb50ca-43cc-401a-8ed1-32ff0c381ed8.xml, kernel.iogetdevicepropertydata, wdm/IoGetDevicePropertyData
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows Vista.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: PowerIrpDDis, HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: <= APC_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - IoGetDevicePropertyData
 - wdm/IoGetDevicePropertyData
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - IoGetDevicePropertyData
---

# IoGetDevicePropertyData function


## -description

The <b>IoGetDevicePropertyData</b> routine retrieves the current setting for a device property.

## -parameters

### -param Pdo 

[in]
A pointer to the physical device object (PDO) for the device that is being queried.

### -param PropertyKey 

[in]
A pointer to a <a href="/previous-versions/windows/hardware/drivers/dn315031(v=vs.85)">DEVPROPKEY</a> structure that specifies the device property key.

### -param Lcid 

[in]
A locale identifier. Set this parameter either to a language-specific LCID value or to <b>LOCALE_NEUTRAL</b>. The <b>LOCALE_NEUTRAL</b> LCID specifies that the property is language-neutral (that is, not specific to any language). Do not set this parameter to <b>LOCALE_SYSTEM_DEFAULT</b> or <b>LOCALE_USER_DEFAULT</b>. For more information about language-specific LCID values, see <a href="/openspecs/windows_protocols/ms-lcid/63d3d639-7fd2-4afb-abbe-0d5b5551eef8">LCID Structure</a>.

### -param Flags

Reserved for system use. Drivers should set this value to 0.

### -param Size 

[in]
The size, in bytes, of the buffer that <i>Data</i> points to.

### -param Data 

[out]
A pointer to the device property data.

### -param RequiredSize 

[out]
A pointer to a ULONG to receive the size of the property information that is returned at <i>Data</i>. If <b>IoGetDevicePropertyData</b> returns STATUS_BUFFER_TOO_SMALL, the caller can use this value to allocate a buffer of the correct size.

### -param Type 

[out]
A pointer to a <a href="/previous-versions/ff543546(v=vs.85)">DEVPROPTYPE</a> value. If <b>IoGetDevicePropertyData</b> completes successfully, the routine uses <i>Type</i> to supply the type of data that is returned in the <i>Data</i> buffer.

## -returns

<b>IoGetDevicePropertyData</b> returns an NTSTATUS value. This routine might return one of the following values:

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
The operation succeeded. The <i>Data</i> buffer contains the retrieved data. *<i>Type</i> contains the type of the retrieved data.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_BUFFER_TOO_SMALL</b></dt>
</dl>
</td>
<td width="60%">
The <i>Data</i> buffer is too small. *<i>RequiredSize</i> contains the required buffer length.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_OBJECT_NAME_NOT_FOUND</b></dt>
</dl>
</td>
<td width="60%">
The specified device property was not found.

</td>
</tr>
</table>

## -remarks

Kernel-mode drivers use the <b>IoGetDevicePropertyData</b> routine to retrieve device properties that are defined as part of the unified device property model.

To see property types available for use by this routine, see [DEVPROP_TYPE_BYTE](/windows-hardware/drivers/install/devprop-type-byte) and adjacent pages for `DEVPROP_TYPE_*`.

Drivers can use the <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-iosetdevicepropertydata">IoSetDevicePropertyData</a> routine to modify a device property.

Callers of <b>IoGetDevicePropertyData</b> must be running at IRQL <= APC_LEVEL in the context of a system thread.

## -see-also

<a href="/previous-versions/windows/hardware/drivers/dn315031(v=vs.85)">DEVPROPKEY</a>



<a href="/previous-versions/ff543546(v=vs.85)">DEVPROPTYPE</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-iosetdevicepropertydata">IoSetDevicePropertyData</a>