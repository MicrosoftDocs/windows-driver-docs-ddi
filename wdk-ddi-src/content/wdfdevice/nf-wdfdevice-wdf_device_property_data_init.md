---
UID: NF:wdfdevice.WDF_DEVICE_PROPERTY_DATA_INIT
title: WDF_DEVICE_PROPERTY_DATA_INIT function (wdfdevice.h)
description: The WDF_DEVICE_PROPERTY_DATA_INIT function initializes a driver's WDF_DEVICE_PROPERTY_DATA structure.
old-location: wdf\wdf_device_property_data_init.htm
tech.root: wdf
ms.assetid: D3A7646A-49A8-499E-A63A-BCD222DF7804
ms.date: 02/26/2018
ms.keywords: WDF_DEVICE_PROPERTY_DATA_INIT, WDF_DEVICE_PROPERTY_DATA_INIT function, wdf.wdf_device_property_data_init, wdfdevice/WDF_DEVICE_PROPERTY_DATA_INIT
ms.topic: function
f1_keywords:
 - "wdfdevice/WDF_DEVICE_PROPERTY_DATA_INIT"
req.header: wdfdevice.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.13
req.umdf-ver: 2.0
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- wdfdevice.h
api_name:
- WDF_DEVICE_PROPERTY_DATA_INIT
product:
- Windows
targetos: Windows
req.typenames: 
---

# WDF_DEVICE_PROPERTY_DATA_INIT function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WDF_DEVICE_PROPERTY_DATA_INIT</b> function initializes a driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdevice/ns-wdfdevice-_wdf_device_property_data">WDF_DEVICE_PROPERTY_DATA</a> structure.


## -parameters




### -param PropertyData [in]

A pointer to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdevice/ns-wdfdevice-_wdf_device_property_data">WDF_DEVICE_PROPERTY_DATA</a> structure.


### -param PropertyKey [in]

A pointer to a <b>DEVPROPKEY</b> structure that specifies the device property key.


## -returns



This function does not return a value.




## -remarks



Before calling the following methods, a driver must call <b>WDF_DEVICE_PROPERTY_DATA_INIT</b> to initialize a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdevice/ns-wdfdevice-_wdf_device_property_data">WDF_DEVICE_PROPERTY_DATA</a> structure.

<ul>
<li>
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdevice/nf-wdfdevice-wdfdeviceallocandquerypropertyex">WdfDeviceAllocAndQueryPropertyEx</a>
</li>
<li>
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdevice/nf-wdfdevice-wdfdeviceassignproperty">WdfDeviceAssignProperty</a>
</li>
<li>
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdevice/nf-wdfdevice-wdfdevicequerypropertyex">WdfDeviceQueryPropertyEx</a>
</li>
<li>
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdffdo/nf-wdffdo-wdffdoinitallocandquerypropertyex">WdfFdoInitAllocAndQueryPropertyEx</a>
</li>
<li>
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdffdo/nf-wdffdo-wdffdoinitquerypropertyex">WdfFdoInitQueryPropertyEx</a>
</li>
</ul>
The <b>WDF_DEVICE_PROPERTY_DATA_INIT</b> function zeros the specified <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdevice/ns-wdfdevice-_wdf_device_property_data">WDF_DEVICE_PROPERTY_DATA</a> structure and sets the structure's <b>Size</b> member. It also sets the structure's <b>PropertyKey</b> member to the specified value.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdevice/ns-wdfdevice-_wdf_device_property_data">WDF_DEVICE_PROPERTY_DATA</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdevice/nf-wdfdevice-wdfdeviceallocandquerypropertyex">WdfDeviceAllocAndQueryPropertyEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdevice/nf-wdfdevice-wdfdeviceassignproperty">WdfDeviceAssignProperty</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdevice/nf-wdfdevice-wdfdevicequerypropertyex">WdfDeviceQueryPropertyEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdffdo/nf-wdffdo-wdffdoinitallocandquerypropertyex">WdfFdoInitAllocAndQueryPropertyEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdffdo/nf-wdffdo-wdffdoinitquerypropertyex">WdfFdoInitQueryPropertyEx</a>
 

 

