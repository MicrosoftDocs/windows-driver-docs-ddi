---
UID: NF:wdfinterrupt.WdfInterruptGetDevice
title: WdfInterruptGetDevice function (wdfinterrupt.h)
description: The WdfInterruptGetDevice method returns a handle to the framework device object that is associated with a specified framework interrupt object.
old-location: wdf\wdfinterruptgetdevice.htm
tech.root: wdf
ms.assetid: c1e7a9ce-5794-4ed0-bb30-e3e68b0251db
ms.date: 02/26/2018
keywords: ["WdfInterruptGetDevice function"]
ms.keywords: DFInterruptObjectRef_9c646459-e17b-434f-b313-d22f3a211c4e.xml, WdfInterruptGetDevice, WdfInterruptGetDevice method, kmdf.wdfinterruptgetdevice, wdf.wdfinterruptgetdevice, wdfinterrupt/WdfInterruptGetDevice
req.header: wdfinterrupt.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.ddi-compliance: DriverCreate
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
req.dll: 
req.irql: <= DIRQL
targetos: Windows
req.typenames: 
f1_keywords:
 - WdfInterruptGetDevice
 - wdfinterrupt/WdfInterruptGetDevice
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
 - WdfInterruptGetDevice
---

# WdfInterruptGetDevice function


## -description

<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WdfInterruptGetDevice</b> method returns a handle to the framework device object that is associated with a specified framework interrupt object.

## -parameters

### -param Interrupt 

[in]
A handle to a framework interrupt object.

## -returns

<b>WdfInterruptGetDevice</b> returns a handle to a framework device object.

A bug check occurs if the driver supplies an invalid object handle.

## -remarks

For more information about handling interrupts in framework-based drivers, see <a href="/windows-hardware/drivers/wdf/handling-hardware-interrupts">Handling Hardware Interrupts</a>.


#### Examples

The following code example shows how an <a href="/windows-hardware/drivers/ddi/wdfinterrupt/nc-wdfinterrupt-evt_wdf_interrupt_isr">EvtInterruptIsr</a> callback function can obtain a pointer to driver-defined context space for the device object that an interrupt object belongs to.

```cpp
BOOLEAN
MyEvtInterruptIsr(
    IN WDFINTERRUPT Interrupt,
    IN ULONG  MessageID
    )
{
    PDEVICE_EXTENSION  devExt;

    devExt = GetMyDeviceContext(WdfInterruptGetDevice(Interrupt));
...
}
```

## -see-also

<a href="/windows-hardware/drivers/ddi/wdfinterrupt/nc-wdfinterrupt-evt_wdf_interrupt_isr">EvtInterruptIsr</a>