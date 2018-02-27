---
UID: NN:portcls.IAdapterPnpManagement
title: IAdapterPnpManagement
author: windows-driver-content
description: IAdapterPnpManagement is an interface that adapters should implement and register if they want to receive PnP management messages.
old-location: audio\iadapterpnpmanagement.htm
old-project: audio
ms.assetid: A5EF8214-76D9-4F4E-A9FE-9374E0EDC9D2
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: IAdapterPnpManagement, IAdapterPnpManagement interface [Audio Devices], IAdapterPnpManagement interface [Audio Devices], described, audio.iadapterpnpmanagement, portcls/IAdapterPnpManagement
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
-	IAdapterPnpManagement
product: Windows
targetos: Windows
req.typenames: PC_EXIT_LATENCY, *PPC_EXIT_LATENCY
---

# IAdapterPnpManagement interface


## -description


<code>IAdapterPnpManagement</code>  is an interface that adapters should implement and
 register if they want to receive PnP management messages.
 Register this interface with PortCls using 
 <a href="..\portcls\nf-portcls-pcregisteradapterpnpmanagement.md">PcRegisterAdapterPnpManagement</a>. Unregister this interface with PortCls using 
 <a href="..\portcls\nf-portcls-pcunregisteradapterpnpmanagement.md">PcUnregisterAdapterPnpManagement</a>.

IAdapterPnpManagement is available in Windows 10, version 1511 and later versions of Windows. 

