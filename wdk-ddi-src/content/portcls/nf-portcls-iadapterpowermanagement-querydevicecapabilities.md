---
UID: NF:portcls.IAdapterPowerManagement.QueryDeviceCapabilities
title: IAdapterPowerManagement::QueryDeviceCapabilities method
author: windows-driver-content
description: The QueryDeviceCapabilities method is called by PortCls in response to a Plug and Play IRP_MN_QUERY_CAPABILITIES IRP.
old-location: audio\iadapterpowermanagement_querydevicecapabilities.htm
old-project: audio
ms.assetid: 79e8cdb8-8c01-4fed-8490-5adeb52c0ea2
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: IAdapterPowerManagement interface [Audio Devices], QueryDeviceCapabilities method, portcls/IAdapterPowerManagement::QueryDeviceCapabilities, QueryDeviceCapabilities method [Audio Devices], IAdapterPowerManagement interface, audio.iadapterpowermanagement_querydevicecapabilities, audmp-routines_e59e3df9-3bfa-4eb0-a7dd-1faa017a48e9.xml, QueryDeviceCapabilities, IAdapterPowerManagement::QueryDeviceCapabilities, QueryDeviceCapabilities method [Audio Devices], IAdapterPowerManagement
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
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
req.lib: portcls.h
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	portcls.h
apiname:
-	IAdapterPowerManagement.QueryDeviceCapabilities
product: Windows
targetos: Windows
req.typenames: PC_EXIT_LATENCY, *PPC_EXIT_LATENCY
---

# IAdapterPowerManagement::QueryDeviceCapabilities method


## -description


The <code>QueryDeviceCapabilities</code> method is called by PortCls in response to a Plug and Play <a href="https://msdn.microsoft.com/library/windows/hardware/ff551664">IRP_MN_QUERY_CAPABILITIES</a> IRP.


## -syntax


````
NTSTATUS QueryDeviceCapabilities(
  [in] PDEVICE_CAPABILITIES PowerDeviceCaps
);
````


## -parameters




### -param PowerDeviceCaps [in]

Pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff543095">DEVICE_CAPABILITIES</a> structure specifying the device's capabilities


## -returns


<code>QueryDeviceCapabilities</code> returns STATUS_SUCCESS if call was successful. Otherwise, the method returns an appropriate error code.



## -remarks


This method is called at driver startup to get the capabilities for the device. The method passes to the adapter driver a capabilities structure that defines the mappings between system power states and device power states. PortCls writes the default values for these mappings into the structure before calling the method. During the call, the adapter driver has the opportunity to edit the mappings, if necessary.

Typically, the adapter driver should not change these settings. If the adapter driver must override the defaults, it can change the mappings to a deeper (less-powered) device power state but not to a weaker (more-powered) device power state. For example, the mappings for S1 (PowerSystemSleeping1) can be changed from D1 to D3, but not to D0.

In order to fill in the <i>PowerDeviceCaps</i> structure for a device, the adapter driver should call <a href="..\portcls\nf-portcls-pcregisteradapterpowermanagement.md">PcRegisterAdapterPowerManagement</a> to register the <b>IAdapterPowerManagement</b> interface at device-startup time. The operating system queries devices before calling the adapter driver's device-startup routine.

In order to change the mappings between system power states and device power states, the adapter driver changes the values in the <b>DeviceState</b> array in the <i>PowerDeviceCaps</i> structure. These mappings should be changed only if necessary. The following code example shows how to map D1 mappings to D3:
<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>  for (i=ULONG(PowerSystemWorking); i&lt;=ULONG(PowerSystemShutdown); i++)
      {
          if (PowerDeviceCaps-&gt;DeviceState[i] == PowerDeviceD1)
          {
              PowerDeviceCaps-&gt;DeviceState[i] = PowerDeviceD3;
          }
      }</pre>
</td>
</tr>
</table></span></div>The code for the <code>QueryDeviceCapabilities</code> method must reside in paged memory.



## -see-also

<a href="..\portcls\nn-portcls-iadapterpowermanagement.md">IAdapterPowerManagement</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff551664">IRP_MN_QUERY_CAPABILITIES</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff543095">DEVICE_CAPABILITIES</a>

<a href="..\portcls\nf-portcls-pcregisteradapterpowermanagement.md">PcRegisterAdapterPowerManagement</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20IAdapterPowerManagement::QueryDeviceCapabilities method%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

