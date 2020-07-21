---
UID: NF:wdm.PcwCreateInstance
title: PcwCreateInstance function (wdm.h)
description: The PcwCreateInstance function creates a new instance for the specified registered counter set.
old-location: devtest\pcwcreateinstance.htm
tech.root: devtest
ms.assetid: ed9bd8fa-a6e6-465a-8415-3e9c19233419
ms.date: 02/23/2018
keywords: ["PcwCreateInstance function"]
ms.keywords: PcwCreateInstance, PcwCreateInstance function [Driver Development Tools], devtest.pcwcreateinstance, km_pcw_32dba149-fed7-4e86-b68c-1f3a6348cb7a.xml, wdm/PcwCreateInstance
f1_keywords:
 - "wdm/PcwCreateInstance"
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows 7 and later versions of Windows.
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
req.irql: <=APC_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- PcwCreateInstance
product:
- Windows
targetos: Windows
req.typenames: 
---

# PcwCreateInstance function

## -description

The `PcwCreateInstance` function creates a new instance for the specified counterset.

## -parameters

### -param Instance [out]

A pointer to receive the newly created instance. The instance should be closed using <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-pcwcloseinstance">PcwCloseInstance</a>.

### -param Registration [in]

A pointer to the counterset registration that owns this instance. The registration is created using <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-pcwregister">PcwRegister</a>

### -param Name [in]

A pointer to the Unicode string that contains the name of the instance of the counterset. Note that instance names are not case-sensitive and should be unique.

### -param Count [in]

The number of data blocks that are associated with this instance.

### -param Data [in]

A pointer to an array of data block descriptors that contains the counter values of this instance.

## -returns

This function returns one of the following values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td>`STATUS_SUCCESS`</td>
<td>
The instance was successfully created.
</td>
</tr>
<tr>
<td>`STATUS_INVALID_PARAMETER_4`</td>
<td>
The number of structures, specified by `Count`, is not valid for the registered provider.
</td>
</tr>
<tr>
<td>`STATUS_INVALID_BUFFER_SIZE`</td>
<td>
A problem was detected with the size of the data buffer and the counter set,
</td>
</tr>
<tr>
<td>`STATUS_INTEGER_OVERFLOW`</td>
<td>
The size of the structure, specified by `Count`, overflows the data buffer,
</td>
</tr>
</table>

## -remarks

Counterset providers can supply information to the consumer through two different systems:

- The provider can supply a `PCW_CALLBACK` function that will be invoked by the Performance Counter Library as needed to collect data. For more information on this system, refer to the documentation for <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-pcw_callback">`PCW_CALLBACK`</a>.
- The provider can use `PcwCreateInstance` and `PcwCloseInstance` to maintain a list of available instances and the corresponding counter data. This system is simple to implement but limited in flexibility. This page explains the usage of `PcwCreateInstance` and `PcwCloseInstance`.

Before the provider uses this function, the provider must call the PcwRegister function to create a registration.

If using the `CTRPP` code generation tool, the developer will typically use the CTRPP-generated Create function instead of calling PcwCreateInstance directly.

When a new instance arrives (e.g. when a device is plugged in), the provider should allocate and initialize a data block for the instance, call `PcwCreateInstance` with the name and data block for the instance, and then keep the values in the data block updated with counter values for the instance. When the instance becomes invalid (e.g. when a device is unplugged), the provider should call `PcwCloseInstance` and then delete the data block.

The provider must maintain data blocks (usually in paged or nonpaged pool) containing the current counter values for each instance.

`PcwCreateInstance` will automatically assign a unique id for the instance. To provide specific values for the instance id, implement a `PCW_CALLBACK` function instead of using `PcwCreateInstance`.

Use the PcwCloseInstance function to close the instance.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-pcwcloseinstance">PcwCloseInstance</a>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-pcwregister">PcwRegister</a>
