---
UID: NF:spbcx.SpbControllerSetRequestAttributes
title: SpbControllerSetRequestAttributes function (spbcx.h)
description: The SpbControllerSetRequestAttributes method sets object attributes that will be used for all SPBREQUEST objects that the SPB framework extension (SpbCx) delivers to the SPB controller driver.
old-location: spb\spbcontrollersetrequestattributes.htm
tech.root: SPB
ms.assetid: 9BE790DB-DB7A-44A3-8A89-673CBFCF4D65
ms.date: 04/30/2018
keywords: ["SpbControllerSetRequestAttributes function"]
ms.keywords: SPB.spbcontrollersetrequestattributes, SpbControllerSetRequestAttributes, SpbControllerSetRequestAttributes method [Buses], spbcx/SpbControllerSetRequestAttributes
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
targetos: Windows
req.typenames: 
f1_keywords:
 - SpbControllerSetRequestAttributes
 - spbcx/SpbControllerSetRequestAttributes
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - spbcxstubs.lib
 - spbcxstubs.dll
api_name:
 - SpbControllerSetRequestAttributes
---

# SpbControllerSetRequestAttributes function


## -description

The <b>SpbControllerSetRequestAttributes</b> method  sets object attributes that will be used for all SPBREQUEST objects  that the SPB framework extension (SpbCx) delivers to the SPB controller driver.

## -parameters

### -param FxDevice 

[in]
A WDFDEVICE handle to the device object that represents the SPB controller.

### -param RequestAttributes 

[in]
A pointer to a caller-allocated <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfobject/ns-wdfobject-_wdf_object_attributes">WDF_OBJECT_ATTRIBUTES</a> structure that contains attributes for the SPB controller's SPBREQUEST objects.

## -remarks

During device initialization, your SPB controller driver can call this method to set the default attributes for SPBREQUEST objects.  Thereafter, SpbCx assigns these attributes to any I/O requests that it delivers (or forwards) to target devices on the bus.

<i>RequestAttributes</i> points to an <b>WDF_OBJECT_ATTRIBUTES</b> structure. The caller must previously have called the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfobject/nf-wdfobject-wdf_object_attributes_init">WDF_OBJECT_ATTRIBUTES_INIT</a> function to initialize this structure. After this call, but before the call to <b>SpbControllerSetRequestAttributes</b>, the caller can change the values of the following members of this structure:

<ul>
<li><b>EvtCleanupCallback</b></li>
<li><b>EvtDestroyCallback</b></li>
<li><b>ContextSizeOverride</b></li>
<li><b>ContextTypeInfo</b></li>
</ul>
<b>SpbControllerSetRequestAttributes</b> will use these values as default attributes for SPBREQUEST objects. However, the driver cannot change the default attribute values that are contained in the <b>ExecutionLevel</b>, <b>SynchronizationScope</b>, and <b>ParentObject</b> members.  These members must remain unchanged from the values that the <b>WDF_OBJECT_ATTRIBUTES_INIT</b> function initializes them to.

<b>WDF_OBJECT_ATTRIBUTES_INIT</b> initializes the <b>EvtCleanupCallback</b> and <b>EvtDestroyCallback</b> members to <b>NULL</b>. If you change these default values to register an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfobject/nc-wdfobject-evt_wdf_object_context_cleanup">EvtCleanupCallback</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfobject/nc-wdfobject-evt_wdf_object_context_destroy">EvtDestroyCallback</a> callback function, this function is called each time an I/O request arrives in the SPB controller queue, which is managed by SpbCx. Such an I/O request causes the <i>EvtCleanupCallback</i> or <i>EvtDestroyCallback</i> function to be called even if SpbCx never presents the request to the SPB controller driver (because the request is canceled after it arrives in the queue but before it is passed to the driver).

The SPB controller driver must call <b>SpbControllerSetRequestAttributes</b> before it <i>commits</i> the device object—that is, before it returns from the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdriver/nc-wdfdriver-evt_wdf_driver_device_add">EvtDriverDeviceAdd</a> callback or adds the PDO to the controller's child list. The child list represents the devices that are attached to the bus. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/enumerating-the-devices-on-a-bus">Enumerating the Devices on a Bus</a>.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdriver/nc-wdfdriver-evt_wdf_driver_device_add">EvtDriverDeviceAdd</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfobject/ns-wdfobject-_wdf_object_attributes">WDF_OBJECT_ATTRIBUTES</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfobject/nf-wdfobject-wdf_object_attributes_init">WDF_OBJECT_ATTRIBUTES_INIT</a>

