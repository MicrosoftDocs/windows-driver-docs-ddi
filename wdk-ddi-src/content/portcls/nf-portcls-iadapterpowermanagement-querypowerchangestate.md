---
UID: NF:portcls.IAdapterPowerManagement.QueryPowerChangeState
title: IAdapterPowerManagement::QueryPowerChangeState (portcls.h)
description: The QueryPowerChangeState method is called by PortCls in response to the receipt of an IRP_MN_QUERY_POWER power IRP.
old-location: audio\iadapterpowermanagement_querypowerchangestate.htm
tech.root: audio
ms.assetid: 32cd29c3-e8da-4119-84a4-3ce4daed528e
ms.date: 05/08/2018
keywords: ["IAdapterPowerManagement::QueryPowerChangeState"]
ms.keywords: IAdapterPowerManagement interface [Audio Devices],QueryPowerChangeState method, IAdapterPowerManagement.QueryPowerChangeState, IAdapterPowerManagement::QueryPowerChangeState, QueryPowerChangeState, QueryPowerChangeState method [Audio Devices], QueryPowerChangeState method [Audio Devices],IAdapterPowerManagement interface, audio.iadapterpowermanagement_querypowerchangestate, audmp-routines_4a5ebdca-faa4-4f99-89d1-6c86a928243c.xml, portcls/IAdapterPowerManagement::QueryPowerChangeState
f1_keywords:
 - "portcls/IAdapterPowerManagement.QueryPowerChangeState"
 - "IAdapterPowerManagement.QueryPowerChangeState"
req.header: portcls.h
req.include-header: Portcls.h
req.target-type: Universal
req.target-min-winverclnt: 
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- portcls.h
api_name:
- IAdapterPowerManagement.QueryPowerChangeState
targetos: Windows
req.typenames: 
---

# IAdapterPowerManagement::QueryPowerChangeState


## -description


The <code>QueryPowerChangeState</code> method is called by PortCls in response to the receipt of an <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mn-query-power">IRP_MN_QUERY_POWER</a> power IRP.


## -parameters




### -param NewStateQuery [in]

Specifies the new power state that is being requested for the device. This parameter is a union of type POWER_STATE. The new power state (<i>NewStateQuery</i>.<b>DeviceState</b>) can be one of the DEVICE_POWER_STATE enumeration values listed in <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nf-portcls-iadapterpowermanagement-powerchangestate">IAdapterPowerManagement::PowerChangeState</a>.


## -returns



<code>QueryPowerChangeState</code> returns STATUS_SUCCESS if call was successful. Otherwise, the method returns an appropriate error code.




## -remarks



PortCls calls the <code>QueryPowerChangeState</code> method on behalf of the system to query the adapter driver for acceptability of a potential device power-state change. The driver can deny the power state change by returning a value other than STATUS_SUCCESS. A call to <code>QueryPowerStateChange</code> is not guaranteed to occur prior to all <b>PowerChangeState</b> calls.

The code for this method must reside in paged memory.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nn-portcls-iadapterpowermanagement">IAdapterPowerManagement</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nf-portcls-iadapterpowermanagement-powerchangestate">IAdapterPowerManagement::PowerChangeState</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mn-query-power">IRP_MN_QUERY_POWER</a>
 

 

