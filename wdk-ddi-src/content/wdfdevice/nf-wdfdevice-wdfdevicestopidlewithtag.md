---
UID: NF:wdfdevice.WdfDeviceStopIdleWithTag
title: WdfDeviceStopIdleWithTag macro (wdfdevice.h)
description: The WdfDeviceStopIdleWithTag macro increments the power reference count for a specified framework device object and assigns the driver's current file name and line number to the reference. The macro also assigns a tag value to the reference.
tech.root: wdf
ms.assetid: 792A5EA8-5273-4284-B0EE-01BE1DCB9863
ms.date: 02/26/2018
ms.keywords: DFDeviceObjectGeneralRef_3dbde224-ecdf-429e-9389-9bdb49b16040.xml, WdfDeviceStopIdleWithTag, WdfDeviceStopIdleWithTag method, kmdf.WdfDeviceStopIdleWithTag, wdf.WdfDeviceStopIdleWithTag, wdfdevice/WdfDeviceStopIdleWithTag
ms.topic: macro
req.header: wdfdevice.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.15
req.umdf-ver: 2.15
req.ddi-compliance: DriverCreate, KmdfIrql, KmdfIrql2
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
req.dll: 
req.irql: See Remarks section.
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Wdf01000.sys
- Wdf01000.sys.dll
- WUDFx02000.dll
- WUDFx02000.dll.dll
api_name:
- WdfDeviceStopIdleWithTag
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfDeviceStopIdleWithTag macro


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The **WdfDeviceStopIdleWithTag** macro increments the power reference count for a specified framework device object and assigns the driver's current file name and line number to the reference. The macro also assigns a tag value to the reference.

## -syntax

```cpp
NTSTATUS WdfDeviceStopIdleWithTag(
    _In_ WDFDEVICE Device,
    _In_ BOOLEAN WaitForD0,
    _In_ PVOID Tag
);
```

## -parameters




### -param Device [in]

A handle to a framework device object.


### -param WaitForD0 [in]

A Boolean value that indicates when **WdfDeviceStopIdleWithTag** will return. If **TRUE**, it returns only after the specified device has entered the D0 device power state. If **FALSE**, the method returns immediately.

### -param Tag [in]

A driver-defined value that the framework stores as an identification tag for the power reference.

## -returns

If the operation succeeds, **WdfDeviceStopIdleWithTag** returns STATUS_SUCCESS.

Additional return values include:

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Return code</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><strong>STATUS_PENDING</strong></td>
<td><p>The device is being powered up asynchronously.</p></td>
</tr>
<tr class="even">
<td><strong>STATUS_INVALID_DEVICE_STATE</strong></td>
<td><p>The driver is not the power policy owner for the device.</p></td>
</tr>
<tr class="odd">
<td><strong>STATUS_POWER_STATE_INVALID</strong></td>
<td><p>A device failure occurred and the device cannot enter its D0 power state.</p></td>
</tr>
</tbody>
</table>

 

The method might return other [NTSTATUS values](https://msdn.microsoft.com/library/windows/hardware/ff557697).

A bug check occurs if the driver supplies an invalid object handle.


## -remarks



If your driver calls **WdfDeviceStopIdleWithTag** to increment a reference count, the driver must call [**WdfDeviceResumeIdleWithTag**](wdfdeviceresumeidlewithtag.md) to decrement the count.

Calling **WdfDeviceStopIdleWithTag** instead of [**WdfDeviceStopIdle**](https://msdn.microsoft.com/library/windows/hardware/ff546921) provides additional information (tag value, line number, and file name) that you can view in Microsoft debuggers. **WdfDeviceStopIdleWithTag** uses the driver's current line number and file name.

You can view the tag, line number, and file name values by using the [**!wdftagtracker**](https://msdn.microsoft.com/library/windows/hardware/ff566126) debugger extension. The debugger extension displays the tag value as both a pointer and a series of characters.

Use [**!wdfkd.wdfdevice**](https://msdn.microsoft.com/library/windows/hardware/ff565703) with verbose flags on and locate the link to [**!wdftagtracker**](https://msdn.microsoft.com/library/windows/hardware/ff566126) in the output:

```cpp
kd> !wdfdevice <handle> f 
```



## -see-also



[Debugging Power Reference Leaks in WDF](https://msdn.microsoft.com/library/windows/hardware/dn965441)

[**WdfDeviceResumeIdle**](https://msdn.microsoft.com/library/windows/hardware/ff546838)

[**WdfDeviceResumeIdleWithTag**](wdfdeviceresumeidlewithtag.md)

[**WdfDeviceStopIdle**](https://msdn.microsoft.com/library/windows/hardware/ff546921)

 

