---
UID: NF:wdffdo.WdfFdoInitSetDefaultChildListConfig
title: WdfFdoInitSetDefaultChildListConfig function (wdffdo.h)
description: The WdfFdoInitSetDefaultChildListConfig method configures a bus driver's default child list.
old-location: wdf\wdffdoinitsetdefaultchildlistconfig.htm
tech.root: wdf
ms.assetid: 656a0c58-dd12-4417-a781-464d1670592c
ms.date: 02/26/2018
ms.keywords: DFDeviceObjectFdoPdoRef_676a2185-db9b-498e-84e3-52b8ac32584c.xml, WdfFdoInitSetDefaultChildListConfig, WdfFdoInitSetDefaultChildListConfig method, kmdf.wdffdoinitsetdefaultchildlistconfig, wdf.wdffdoinitsetdefaultchildlistconfig, wdffdo/WdfFdoInitSetDefaultChildListConfig
ms.topic: function
f1_keywords:
 - "wdffdo/WdfFdoInitSetDefaultChildListConfig"
req.header: wdffdo.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 
req.ddi-compliance: ChildListConfiguration, DeviceInitAPI, DriverCreate, KmdfIrql, KmdfIrql2
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (see Framework Library Versioning.)
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Wdf01000.sys
- Wdf01000.sys.dll
api_name:
- WdfFdoInitSetDefaultChildListConfig
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfFdoInitSetDefaultChildListConfig function


## -description


<p class="CCE_Message">[Applies to KMDF only]</p>

The <b>WdfFdoInitSetDefaultChildListConfig</b> method configures a bus driver's default child list.


## -parameters




### -param DeviceInit [in, out]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/wdfdevice_init">WDFDEVICE_INIT</a> structure that the driver obtained from its <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdriver/nc-wdfdriver-evt_wdf_driver_device_add">EvtDriverDeviceAdd</a> callback function.


### -param Config [in]

A pointer to a driver-allocated <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfchildlist/ns-wdfchildlist-_wdf_child_list_config">WDF_CHILD_LIST_CONFIG</a> structure.


### -param DefaultChildListAttributes [in, optional]

A pointer to a caller-allocated <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfobject/ns-wdfobject-_wdf_object_attributes">WDF_OBJECT_ATTRIBUTES</a> structure that contains object attributes for the child-list object that represents the driver's default child list. This parameter is optional and can be WDF_NO_OBJECT_ATTRIBUTES.


## -returns



None




## -remarks



A bus driver must call <b>WdfFdoInitSetDefaultChildListConfig</b> before calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdevice/nf-wdfdevice-wdfdevicecreate">WdfDeviceCreate</a> for the functional device object (FDO). For more information about calling <b>WdfDeviceCreate</b>, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/creating-a-framework-device-object">Creating a Framework Device Object</a>.

For more information about the <b>WdfFdoInitSetDefaultChildListConfig</b> method, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/enumerating-the-devices-on-a-bus">Enumerating the Devices on a Bus</a>.


#### Examples

The following code example initializes a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfchildlist/ns-wdfchildlist-_wdf_child_list_config">WDF_CHILD_LIST_CONFIG</a> structure and then calls <b>WdfFdoInitSetDefaultChildListConfig</b>. 

```cpp
WDF_CHILD_LIST_CONFIG  config;

WDF_CHILD_LIST_CONFIG_INIT(
                           &config,
 sizeof(MY_IDENTIFICATION_DESCRIPTION),
                           My_EvtDeviceListCreatePdo
                           );
config.EvtChildListIdentificationDescriptionDuplicate = My_EvtChildListIdentificationDescriptionDuplicate;
config.EvtChildListIdentificationDescriptionCompare = My_EvtChildListIdentificationDescriptionCompare;
config.EvtChildListIdentificationDescriptionCleanup = My_EvtChildListIdentificationDescriptionCleanup;

WdfFdoInitSetDefaultChildListConfig(
                                    DeviceInit,
                                    &config,
                                    WDF_NO_OBJECT_ATTRIBUTES
                                    );
```



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfchildlist/nf-wdfchildlist-wdf_child_list_config_init">WDF_CHILD_LIST_CONFIG_INIT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfchildlist/nf-wdfchildlist-wdfchildlistcreate">WdfChildListCreate</a>
 

 

