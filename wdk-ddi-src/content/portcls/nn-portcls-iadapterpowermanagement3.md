---
UID: NN:portcls.IAdapterPowerManagement3
title: IAdapterPowerManagement3
author: windows-driver-content
description: The IAdapterPowerManagement3 interface inherits from IUnknown, and it is used for receiving power management messages.
old-location: audio\iadapterpowermanagement3.htm
old-project: audio
ms.assetid: 5F0729DB-C991-4745-9550-9D25D6836A1F
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: IAdapterPowerManagement3, IAdapterPowerManagement3 interface [Audio Devices], IAdapterPowerManagement3 interface [Audio Devices],described, audio.iadapterpowermanagement3, portcls/IAdapterPowerManagement3
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: interface
req.header: portcls.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	Portcls.h
api_name:
-	IAdapterPowerManagement3
product: Windows
targetos: Windows
req.typenames: 
---

# IAdapterPowerManagement3 interface


## -description


The IAdapterPowerManagement3 interface inherits from <b>IUnknown</b>, and it is used for receiving power management messages.

To register this interface with PortCls, the adapter driver must call  <a href="https://msdn.microsoft.com/library/windows/hardware/ff537724">PcRegisterAdapterPowerManagement</a>.
<div class="alert"><b>Note</b>  If you want to fill the <a href="http://go.microsoft.com/fwlink/p/?linkid=143127">caps structure</a> for your device, your adapter driver can call <b>PcRegisterAdapterPowerManagement</b> from within the <a href="http://msdn.microsoft.com/en-us/library/windows/hardware/ff540521(v=vs.85).aspx">AddDevice</a> routine, or before your driver calls <b>AddDevice.</b></div><div> </div>

## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IAdapterPowerManagement3</b> interface inherits from the <a href="https://msdn.microsoft.com/33f1d79a-33fc-4ce5-a372-e08bda378332">IUnknown</a> interface. <b>IAdapterPowerManagement3</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -members

The <b>IAdapterPowerManagement3</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/jj200331">D3ExitLatencyChanged</a>
</td>
<td align="left" width="63%">
PortCls calls the D3ExitLatencyChanged method while the device is in sleep (D3) power state, to provide a new exit latency value.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/jj200332">PowerChangeState3</a>
</td>
<td align="left" width="63%">
PortCls calls the PowerChangeState3 method to request a change to the new power state. This request is passed on to the adapter driver.

</td>
</tr>
</table> 


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff536486">IAdapterPowerManagement2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff537724">PcRegisterAdapterPowerManagement</a>
 

 

