---
UID: NF:spbcx.SpbControllerSetTargetAttributes
title: SpbControllerSetTargetAttributes function (spbcx.h)
description: The SpbControllerSetTargetAttributes method sets object attributes that will be used for all SPBTARGET objects that the SPB framework extension (SpbCx) delivers to the SPB controller driver.
old-location: spb\spbcontrollersettargetattributes.htm
tech.root: SPB
ms.assetid: 8EC415AA-F578-42BF-B785-52613B20A2AC
ms.date: 04/30/2018
keywords: ["SpbControllerSetTargetAttributes function"]
ms.keywords: SPB.spbcontrollersettargetattributes, SpbControllerSetTargetAttributes, SpbControllerSetTargetAttributes method [Buses], spbcx/SpbControllerSetTargetAttributes
f1_keywords:
 - "spbcx/SpbControllerSetTargetAttributes"
 - "SpbControllerSetTargetAttributes"
req.header: spbcx.h
req.include-header: 
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 8.
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
req.lib: Spbcxstubs.lib
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- spbcxstubs.lib
- spbcxstubs.dll
api_name:
- SpbControllerSetTargetAttributes
targetos: Windows
req.typenames: 
---

# SpbControllerSetTargetAttributes function


## -description


The <b>SpbControllerSetTargetAttributes</b> method sets object attributes that will be used for all SPBTARGET objects that the SPB framework extension (SpbCx) delivers to the SPB controller driver.


## -parameters




### -param FxDevice 
[in]
A WDFDEVICE handle to the device object that represents the SPB controller.


### -param ObjectAttributes 
[in]
A pointer to a caller-allocated <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfobject/ns-wdfobject-_wdf_object_attributes">WDF_OBJECT_ATTRIBUTES</a> structure that contains attributes for the controller's SPBTARGET objects.


## -remarks



Your SPB controller driver calls this method to set the default attributes for SPBTARGET objects.  The SPB framework extension (SpbCx) sets these attributes on any target devices on the bus that are opened by clients (peripheral devices) of the controller.

<i>ObjectAttributes</i> points to an <b>WDF_OBJECT_ATTRIBUTES</b> structure. The caller must previously have called the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfobject/nf-wdfobject-wdf_object_attributes_init">WDF_OBJECT_ATTRIBUTES_INIT</a> function to initialize this structure. After this call, but before the call to <b>SpbControllerSetTargetAttributes</b>, the caller can change the values of the following members of this structure:

<ul>
<li><b>EvtCleanupCallback</b></li>
<li><b>EvtDestroyCallback</b></li>
<li><b>ContextSizeOverride</b></li>
<li><b>ContextTypeInfo</b></li>
</ul>
<b>SpbControllerSetTargetAttributes</b> will use these values as default attributes for SPBTARGET objects. However, the driver cannot change the default attribute values that are contained in the <b>ExecutionLevel</b>, <b>SynchronizationScope</b>, and <b>ParentObject</b> members.  These members must remain unchanged from the values that they were initialized to by the <b>WDF_OBJECT_ATTRIBUTES_INIT</b> function.

The SPB controller driver must call this method before it <i>commits</i> the device object—that is, before it returns from the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdriver/nc-wdfdriver-evt_wdf_driver_device_add">EvtDriverDeviceAdd</a> callback or adds the PDO to the controller's child list. The child list represents the devices that are attached to the bus. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/enumerating-the-devices-on-a-bus">Enumerating the Devices on a Bus</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdriver/nc-wdfdriver-evt_wdf_driver_device_add">EvtDriverDeviceAdd</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfobject/ns-wdfobject-_wdf_object_attributes">WDF_OBJECT_ATTRIBUTES</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfobject/nf-wdfobject-wdf_object_attributes_init">WDF_OBJECT_ATTRIBUTES_INIT</a>
 

 

