---
UID: NF:portcls.IPortClsPnp.RegisterAdapterPnpManagement
title: IPortClsPnp::RegisterAdapterPnpManagement method
author: windows-driver-content
description: The RegisterAdapterPowerManagement method registers the PnP management interface of the adapter with PortCls.
old-location: audio\iportclspnp_registeradapterpnpmanagement.htm
old-project: audio
ms.assetid: D9A54562-0ABC-4BEA-A9E3-F1A0A4EBC095
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: IPortClsPnp, IPortClsPnp::RegisterAdapterPnpManagement, RegisterAdapterPnpManagement
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: portcls.h
req.include-header: Portcls.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows 10, version 1511 and later versions of Windows.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IPortClsPnp.RegisterAdapterPnpManagement
req.alt-loc: portcls.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
req.typenames: PC_EXIT_LATENCY, *PPC_EXIT_LATENCY
---

# IPortClsPnp::RegisterAdapterPnpManagement method



## -description
The <code>RegisterAdapterPowerManagement</code> method registers the PnP management interface of the adapter with PortCls.



## -syntax

````
NTSTATUS RegisterAdapterPnpManagement(
  [in] PUNKNOWN       pUnknown,
  [in] PDEVICE_OBJECT DeviceObject
);
````


## -parameters

### -param pUnknown [in]

Specifies a pointer to <b>IUnknown</b> of <a href="..\portcls\nn-portcls-iadapterpnpmanagement.md">IAdapterPnpManagement</a>. 


### -param DeviceObject [in]

Specifies a pointer to a <a href="..\wdm\ns-wdm-_device_object.md">DEVICE_OBJECT</a> structure that represents the functional device object of the adapter.


## -returns
The <code>RegisterAdapterPowerManagement</code> method returns STATUS_SUCCESS if the call is successful. Otherwise, it returns the appropriate error code.


## -remarks
When the <code>RegisterAdapterPowerManagement</code> method registers the PnP management interface for the adapter with PortCls, it allows the adapter driver to be notified of PnP state change events.

For more information,  see <a href="https://msdn.microsoft.com/FCAD7F8B-AA9B-430A-BCAF-04E13FA15382">Implement PnP Rebalance for PortCls Audio Drivers</a>.


## -see-also
<dl>
<dt>
<a href="..\portcls\nn-portcls-iportclspnp.md">IPortClsPnp</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff536876">IPortClsPower::UnregisterAdapterPowerManagement</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20IPortClsPnp::RegisterAdapterPnpManagement method%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

