---
UID: NF:ucmmanager.UcmConnectorCreate
title: UcmConnectorCreate function (ucmmanager.h)
description: Creates a connector object.
old-location: buses\ucmconnectorcreate.htm
tech.root: usbref
ms.assetid: 1376CB84-05F6-4903-B245-A00CFA9B228E
ms.date: 05/07/2018
ms.keywords: UcmConnectorCreate, UcmConnectorCreate method [Buses], buses.ucmconnectorcreate, ucmmanager/UcmConnectorCreate
ms.topic: function
req.header: ucmmanager.h
req.include-header: Ucmcx.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 1.15
req.umdf-ver: 2.15
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: UcmCxstub.lib
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- UcmCxstub.lib
- UcmCxstub.dll
api_name:
- UcmConnectorCreate
product:
- Windows
targetos: Windows
req.typenames: 
---

# UcmConnectorCreate function


## -description


Creates a connector object.


## -parameters




### -param WdfDevice [in]

A handle to a framework device object that the client driver received in the previous call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdevice/nf-wdfdevice-wdfdevicecreate">WdfDeviceCreate</a>.


### -param Config [in]

A pointer to a caller-supplied <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ucmmanager/ns-ucmmanager-_ucm_connector_config">UCM_CONNECTOR_CONFIG</a> structure that is initialized by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ucmmanager/nf-ucmmanager-ucm_connector_config_init">UCM_CONNECTOR_CONFIG_INIT</a>.


### -param Attributes [in]

A pointer to a caller-supplied <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfobject/ns-wdfobject-_wdf_object_attributes">WDF_OBJECT_ATTRIBUTES</a> structure that contains attributes for the new connector object. This parameter is optional and can be WDF_NO_OBJECT_ATTRIBUTES.




### -param Connector [out]

A pointer to a location that receives a handle to the new connector object.




## -returns



<b>UcmConnectorCreate</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method can return an appropriate <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS</a> value. 




## -remarks



If the client driver specifies a connector identifier that is already in use, the method fails with STATUS_INVALID_PARAMETER error code.

If the Type-C connector is specified to be a Dual-Role port (DRP), the client driver must register its <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ucmmanager/nc-ucmmanager-evt_ucm_connector_set_data_role">EVT_UCM_CONNECTOR_SET_DATA_ROLE</a> event callback.  

The parent object is WdfDevice. You can set the <b>ParentObject</b> member of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfobject/ns-wdfobject-_wdf_object_attributes">WDF_OBJECT_ATTRIBUTES</a> to NULL or the WDFDEVICE handle. The connector object gets deleted when the parent WDFDEVICE object gets deleted.

An appropriate place for a UCM client driver to call <b>UcmConnectorCreate</b> is in <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdevice/nc-wdfdevice-evt_wdf_device_prepare_hardware">EvtDevicePrepareHardware</a>  or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdevice/nc-wdfdevice-evt_wdf_device_d0_entry">EvtDeviceD0Entry</a>. Conversely, the driver should release the UCMCONNECTOR  handle in  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdevice/nc-wdfdevice-evt_wdf_device_release_hardware">EvtDeviceReleaseHardware</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdevice/nc-wdfdevice-evt_wdf_device_d0_exit">EvtDeviceD0Exit</a>.


#### Examples

This example code shows how to create a Type-C connector that is PD-capable.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>    
    UCMCONNECTOR Connector;
  
    UCM_CONNECTOR_CONFIG_INIT(&connCfg, 0);

    UCM_CONNECTOR_TYPE_C_CONFIG_INIT(
        &connCfg.TypeCConfig,
        UcmTypeCOperatingModeDrp,
        UcmTypeCCurrentDefaultUsb | UcmTypeCCurrent1500mA | UcmTypeCCurrent3000mA);

    connCfg.EvtSetDataRole = EvtSetDataRole;

    UCM_CONNECTOR_PD_CONFIG_INIT(&connCfg.PdConfig, UcmPowerRoleSink | UcmPowerRoleSource);

    WDF_OBJECT_ATTRIBUTES_INIT_CONTEXT_TYPE(&attr, CONNECTOR_CONTEXT);

    status = UcmConnectorCreate(Device, &connCfg, &attr, &Connector);
    if (!NT_SUCCESS(status))
    {
        TRACE_ERROR(
            "UcmConnectorCreate failed with %!STATUS!.",
            status);
        goto Exit;
    }

    TRACE_INFO("UcmConnectorCreate() succeeded.");
</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ucmmanager/ns-ucmmanager-_ucm_connector_config">UCM_CONNECTOR_CONFIG</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ucmmanager/nf-ucmmanager-ucm_connector_config_init">UCM_CONNECTOR_CONFIG_INIT</a>
 

 

