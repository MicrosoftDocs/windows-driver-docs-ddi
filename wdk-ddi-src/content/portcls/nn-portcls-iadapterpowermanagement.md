---
UID: NN:portcls.IAdapterPowerManagement
title: IAdapterPowerManagement
author: windows-driver-content
description: The IAdapterPowerManagement interface is used to manage the power state of an audio adapter.
old-location: audio\iadapterpowermanagement.htm
old-project: audio
ms.assetid: 20c898fd-a782-4d73-bf1b-a25db4440632
ms.author: windowsdriverdev
ms.date: 3/19/2018
ms.keywords: IAdapterPowerManagement, IAdapterPowerManagement interface [Audio Devices], IAdapterPowerManagement interface [Audio Devices], described, audio.iadapterpowermanagement, audmp-routines_9daec120-c61d-426c-b30f-80484e1fb652.xml, portcls/IAdapterPowerManagement
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	portcls.h
api_name:
-	IAdapterPowerManagement
product: Windows
targetos: Windows
req.typenames: PC_EXIT_LATENCY, *PPC_EXIT_LATENCY
---

# IAdapterPowerManagement interface


## -description


The <code>IAdapterPowerManagement</code> interface is used to manage the power state of an audio adapter. This interface is implemented by the adapter driver, which exposes the interface to the PortCls system driver. <code>IAdapterPowerManagement</code> inherits from the <b>IUnknown</b> interface.

The operating system manages power in a WDM audio adapter primarily through the <code>IAdapterPowerManagement</code> interface that the adapter driver registers with PortCls during the device-startup phase of device initialization (see <a href="https://msdn.microsoft.com/library/windows/hardware/ff563849">Starting a Device</a>). The adapter driver registers its <code>IAdapterPowerManagement</code> interface by calling the PortCls function <a href="https://msdn.microsoft.com/library/windows/hardware/ff537724">PcRegisterAdapterPowerManagement</a>. This function receives an <b>IUnknown</b> object from the adapter driver and determines whether the object supports the <code>IAdapterPowerManagement</code> interface by calling <b>QueryInterface</b> on this object with REFIID <b>IID_IAdapterPowerManagement</b>.

For more information, see <a href="https://msdn.microsoft.com/654b86a7-845c-415b-99e4-c7be92cb9b9c">Implementing IAdapterPowerManagement</a>.

