---
UID: NN:portcls.IAdapterPowerManagement2
title: IAdapterPowerManagement2
author: windows-driver-content
description: The IAdapterPowerManagement2 interface inherits from IUnknown and it is used to manage the power state of an audio adapter.
old-location: audio\iadapterpowermanagement2.htm
old-project: audio
ms.assetid: 86cab3f1-2792-486f-91a3-4fb88be2a1da
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: PcUnregisterIoTimeout
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: interface
req.header: portcls.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IAdapterPowerManagement2
req.alt-loc: portcls.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Portcls.lib
req.dll: 
req.irql: PASSIVE_LEVEL
req.typenames: PC_EXIT_LATENCY, *PPC_EXIT_LATENCY
---

# IAdapterPowerManagement2 interface



## -description
The <code>IAdapterPowerManagement2</code> interface inherits from <b>IUnknown</b> and it is used to manage the power state of an audio adapter. In contrast with the <a href="..\portcls\nn-portcls-iadapterpowermanagement.md">IAdapterPowerManagement</a> interface, <code>IAdapterPowerManagement2</code> provides the adapter driver with messages about device and system power states. This enables the driver to make more efficient power management adjustments.

<code>IAdapterPowerManagement2</code> is implemented by the audio adapter driver and the driver must register this interface with Portcls.sys (Portcls) so that it can receive power management messages. To register this interface, the driver must call <a href="..\portcls\nf-portcls-pcregisteradapterpowermanagement.md">PcRegisterAdapterPowerManagement</a>. If you want to fill the <a href="http://go.microsoft.com/fwlink/p/?linkid=143127">caps structure</a> for your device, your adapter driver can call <b>PcRegisterAdapterPowerManagement</b> from within the <a href="https://msdn.microsoft.com/library/windows/hardware/ff540521">AddDevice</a> function or before your driver calls <b>AddDevice</b>.



## -inheritance
The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IAdapterPowerManagement2</b> interface inherits from the <a href="com.iunknown" xmlns:loc="http://microsoft.com/wdcml/l10n"><b>IUnknown</b></a> interface but does not have additional members.


## -remarks
