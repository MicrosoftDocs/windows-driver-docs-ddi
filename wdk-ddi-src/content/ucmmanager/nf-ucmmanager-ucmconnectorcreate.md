---
UID: NF:ucmmanager.UcmConnectorCreate
title: UcmConnectorCreate function
author: windows-driver-content
description: Creates a connector object.
old-location: buses\ucmconnectorcreate.htm
old-project: usbref
ms.assetid: 1376CB84-05F6-4903-B245-A00CFA9B228E
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: UcmConnectorCreate, UcmConnectorCreate method [Buses], buses.ucmconnectorcreate, ucmmanager/UcmConnectorCreate
ms.prod: windows-hardware
ms.technology: windows-devices
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
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	UcmCxstub.lib
-	UcmCxstub.dll
api_name:
-	UcmConnectorCreate
product: Windows
targetos: Windows
req.typenames: PORT_DATA_1, *PPORT_DATA_1
req.product: Windows 10 or later.
---

# UcmConnectorCreate function


## -description


Creates a connector object.


## -parameters




### -param WdfDevice [in]

A handle to a framework device object that the client driver received in the previous call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff545926">WdfDeviceCreate</a>.


### -param Config [in]

A pointer to a caller-supplied <a href="https://msdn.microsoft.com/library/windows/hardware/mt187922">UCM_CONNECTOR_CONFIG</a> structure that is initialized by calling <a href="https://msdn.microsoft.com/library/windows/hardware/mt187923">UCM_CONNECTOR_CONFIG_INIT</a>.


### -param Attributes [in]

A pointer to a caller-supplied <a href="https://msdn.microsoft.com/library/windows/hardware/ff552400">WDF_OBJECT_ATTRIBUTES</a> structure that contains attributes for the new connector object. This parameter is optional and can be WDF_NO_OBJECT_ATTRIBUTES.




### -param Connector [out]

A pointer to a location that receives a handle to the new connector object.




## -returns



<b>UcmConnectorCreate</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method can return an appropriate <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a> value. 




## -remarks



If the client driver specifies a connector identifier that is already in use, the method fails with STATUS_INVALID_PARAMETER error code.

If the Type-C connector is specified to be a Dual-Role port (DRP), the client driver must register its <a href="https://msdn.microsoft.com/library/windows/hardware/mt187818">EVT_UCM_CONNECTOR_SET_DATA_ROLE</a> event callback.  

The parent object is WdfDevice. You can set the <b>ParentObject</b> member of <a href="https://msdn.microsoft.com/library/windows/hardware/ff552400">WDF_OBJECT_ATTRIBUTES</a> to NULL or the WDFDEVICE handle. The connector object gets deleted when the parent WDFDEVICE object gets deleted.

An appropriate place for a UCM client driver to call <b>UcmConnectorCreate</b> is in <a href="https://msdn.microsoft.com/a3d4a983-8a75-44be-bd72-8673d89f9f87">EvtDevicePrepareHardware</a>  or <a href="https://msdn.microsoft.com/0cfabb0f-2d5e-4445-8683-d2916de5b549">EvtDeviceD0Entry</a>. Conversely, the driver should release the UCMCONNECTOR  handle in  <a href="https://msdn.microsoft.com/b4c17e57-688c-4c76-892c-5c8abbf83f20">EvtDeviceReleaseHardware</a> or <a href="https://msdn.microsoft.com/bc3af732-f9ab-43a4-bc6f-7fa0b4c05a66">EvtDeviceD0Exit</a>.


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
  
    UCM_CONNECTOR_CONFIG_INIT(&amp;connCfg, 0);

    UCM_CONNECTOR_TYPE_C_CONFIG_INIT(
        &amp;connCfg.TypeCConfig,
        UcmTypeCOperatingModeDrp,
        UcmTypeCCurrentDefaultUsb | UcmTypeCCurrent1500mA | UcmTypeCCurrent3000mA);

    connCfg.EvtSetDataRole = EvtSetDataRole;

    UCM_CONNECTOR_PD_CONFIG_INIT(&amp;connCfg.PdConfig, UcmPowerRoleSink | UcmPowerRoleSource);

    WDF_OBJECT_ATTRIBUTES_INIT_CONTEXT_TYPE(&amp;attr, CONNECTOR_CONTEXT);

    status = UcmConnectorCreate(Device, &amp;connCfg, &amp;attr, &amp;Connector);
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




<a href="https://msdn.microsoft.com/library/windows/hardware/mt187922">UCM_CONNECTOR_CONFIG</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt187923">UCM_CONNECTOR_CONFIG_INIT</a>
 

 

