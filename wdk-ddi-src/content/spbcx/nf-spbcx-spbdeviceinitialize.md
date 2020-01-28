---
UID: NF:spbcx.SpbDeviceInitialize
title: SpbDeviceInitialize function (spbcx.h)
description: The SpbDeviceInitialize method completes the initialization of the SPB controller driver after this driver creates the associated device object.
old-location: spb\spbdeviceinitialize.htm
tech.root: SPB
ms.assetid: 2EB57066-164F-445C-8621-7B65E6715E97
ms.date: 04/30/2018
ms.keywords: SPB.spbdeviceinitialize, SpbDeviceInitialize, SpbDeviceInitialize method [Buses], spbcx/SpbDeviceInitialize
f1_keywords:
 - "spbcx/SpbDeviceInitialize"
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
- SpbDeviceInitialize
product:
- Windows
targetos: Windows
req.typenames: 
---

# SpbDeviceInitialize function


## -description


The <b>SpbDeviceInitialize</b> method completes the initialization of the SPB controller driver after this driver creates the associated device object.


## -parameters




### -param FxDevice [in]

A WDFDEVICE handle to the device object that represents the SPB controller.


### -param Config [in]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/spbcx/ns-spbcx-_spb_controller_config">SPB_CONTROLLER_CONFIG</a> structure that contains the device configuration information for the SPB controller driver.  This structure must have been initialized by the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/spbcx/nf-spbcx-spb_controller_config_init">SPB_CONTROLLER_CONFIG_INIT</a> function.


## -returns



<b>SpbDeviceInitialize</b> returns STATUS_SUCCESS if it succeeds. Otherwise, it returns an appropriate NTSTATUS error code.




## -remarks



Your SPB controller driver calls this method to register its event callback functions with the SPB framework extension (SpbCx) and to specify the transfer mode to use for the controller's I/O queue. <b>SpbDeviceInitialize</b> creates all of the controller's internal data structures, including the I/O queue.

The SPB controller driver must call this method before it <i>commits</i> the device object—that is, before it returns from the <i>EvtDriverDeviceAdd</i> callback or adds the PDO to the controller's child list. The child list represents the devices that are attached to the bus. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/enumerating-the-devices-on-a-bus">Enumerating the Devices on a Bus</a>.

After <b>SpbDeviceInitialize</b> returns, the controller is ready to process I/O requests, but the SPB controller driver can, as needed, continue to configure the controller settings before it commits the device object.

If the structure pointed to by <i>Config</i> is not filled out correctly, <a href="https://docs.microsoft.com/windows-hardware/drivers/what-s-new-in-driver-development">Driver Verifier</a> will raise an error. For more information about the requirements for the <i>Config</i> parameter, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/spbcx/ns-spbcx-_spb_controller_config">SPB_CONTROLLER_CONFIG</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfchildlist/nc-wdfchildlist-evt_wdf_child_list_create_device">EvtChildListCreateDevice</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdriver/nc-wdfdriver-evt_wdf_driver_device_add">EvtDriverDeviceAdd</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/spbcx/ns-spbcx-_spb_controller_config">SPB_CONTROLLER_CONFIG</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/spbcx/nf-spbcx-spb_controller_config_init">SPB_CONTROLLER_CONFIG_INIT</a>
 

 

