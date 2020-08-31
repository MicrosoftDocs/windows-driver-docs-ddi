---
UID: NN:portcls.IAdapterPnpManagement
title: IAdapterPnpManagement (portcls.h)
description: IAdapterPnpManagement is an interface that adapters should implement and register if they want to receive PnP management messages.
old-location: audio\iadapterpnpmanagement.htm
tech.root: audio
ms.assetid: A5EF8214-76D9-4F4E-A9FE-9374E0EDC9D2
ms.date: 03/19/2018
keywords: ["IAdapterPnpManagement interface"]
ms.keywords: IAdapterPnpManagement, IAdapterPnpManagement interface [Audio Devices], IAdapterPnpManagement interface [Audio Devices], described, audio.iadapterpnpmanagement, portcls/IAdapterPnpManagement
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
targetos: Windows
req.typenames: PC_EXIT_LATENCY, *PPC_EXIT_LATENCY
f1_keywords:
 - IAdapterPnpManagement
 - portcls/IAdapterPnpManagement
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - portcls.h
api_name:
 - IAdapterPnpManagement
---

# IAdapterPnpManagement interface


## -description

<code>IAdapterPnpManagement</code>  is an interface that adapters should implement and
 register if they want to receive PnP management messages.
 Register this interface with PortCls using
 <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nf-portcls-pcregisteradapterpnpmanagement">PcRegisterAdapterPnpManagement</a>. Unregister this interface with PortCls using
 <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nf-portcls-pcunregisteradapterpnpmanagement">PcUnregisterAdapterPnpManagement</a>.

IAdapterPnpManagement is available in Windows 10, version 1511 and later versions of Windows.

