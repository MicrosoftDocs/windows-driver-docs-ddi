---
UID: NF:portcls.IAdapterPowerManagement.QueryDeviceCapabilities
title: IAdapterPowerManagement::QueryDeviceCapabilities (portcls.h)
description: The QueryDeviceCapabilities method is called by PortCls in response to a Plug and Play IRP_MN_QUERY_CAPABILITIES IRP.
old-location: audio\iadapterpowermanagement_querydevicecapabilities.htm
tech.root: audio
ms.assetid: 79e8cdb8-8c01-4fed-8490-5adeb52c0ea2
ms.date: 05/08/2018
ms.keywords: IAdapterPowerManagement interface [Audio Devices],QueryDeviceCapabilities method, IAdapterPowerManagement.QueryDeviceCapabilities, IAdapterPowerManagement::QueryDeviceCapabilities, QueryDeviceCapabilities, QueryDeviceCapabilities method [Audio Devices], QueryDeviceCapabilities method [Audio Devices],IAdapterPowerManagement interface, audio.iadapterpowermanagement_querydevicecapabilities, audmp-routines_e59e3df9-3bfa-4eb0-a7dd-1faa017a48e9.xml, portcls/IAdapterPowerManagement::QueryDeviceCapabilities
f1_keywords:
 - "portcls/IAdapterPowerManagement.QueryDeviceCapabilities"
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
- IAdapterPowerManagement.QueryDeviceCapabilities
product:
- Windows
targetos: Windows
req.typenames: 
---

# IAdapterPowerManagement::QueryDeviceCapabilities


## -description


The <code>QueryDeviceCapabilities</code> method is called by PortCls in response to a Plug and Play <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mn-query-capabilities">IRP_MN_QUERY_CAPABILITIES</a> IRP.


## -parameters




### -param PowerDeviceCaps [in]

Pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_device_capabilities">DEVICE_CAPABILITIES</a> structure specifying the device's capabilities


## -returns



<code>QueryDeviceCapabilities</code> returns STATUS_SUCCESS if call was successful. Otherwise, the method returns an appropriate error code.




## -remarks



This method is called at driver startup to get the capabilities for the device. The method passes to the adapter driver a capabilities structure that defines the mappings between system power states and device power states. PortCls writes the default values for these mappings into the structure before calling the method. During the call, the adapter driver has the opportunity to edit the mappings, if necessary.

Typically, the adapter driver should not change these settings. If the adapter driver must override the defaults, it can change the mappings to a deeper (less-powered) device power state but not to a weaker (more-powered) device power state. For example, the mappings for S1 (PowerSystemSleeping1) can be changed from D1 to D3, but not to D0.

In order to fill in the <i>PowerDeviceCaps</i> structure for a device, the adapter driver should call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nf-portcls-pcregisteradapterpowermanagement">PcRegisterAdapterPowerManagement</a> to register the <b>IAdapterPowerManagement</b> interface at device-startup time. The operating system queries devices before calling the adapter driver's device-startup routine.

In order to change the mappings between system power states and device power states, the adapter driver changes the values in the <b>DeviceState</b> array in the <i>PowerDeviceCaps</i> structure. These mappings should be changed only if necessary. The following code example shows how to map D1 mappings to D3:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>  for (i=ULONG(PowerSystemWorking); i<=ULONG(PowerSystemShutdown); i++)
      {
          if (PowerDeviceCaps->DeviceState[i] == PowerDeviceD1)
          {
              PowerDeviceCaps->DeviceState[i] = PowerDeviceD3;
          }
      }</pre>
</td>
</tr>
</table></span></div>
The code for the <code>QueryDeviceCapabilities</code> method must reside in paged memory.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_device_capabilities">DEVICE_CAPABILITIES</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nn-portcls-iadapterpowermanagement">IAdapterPowerManagement</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mn-query-capabilities">IRP_MN_QUERY_CAPABILITIES</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nf-portcls-pcregisteradapterpowermanagement">PcRegisterAdapterPowerManagement</a>
 

 

