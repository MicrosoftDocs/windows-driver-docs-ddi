---
UID: NN:portcls.IPortClsNotifications
title: IPortClsNotifications (portcls.h)
description: An interface implemented by ports to provide notification helpers to miniports to support audio module communication.
old-location: audio\iportclsnotifications.htm
tech.root: audio
ms.assetid: 03F65E4E-C942-4748-8D3E-938A6AC51B2A
ms.date: 05/08/2018
keywords: ["IPortClsNotifications interface"]
ms.keywords: IPortClsNotifications, IPortClsNotifications interface [Audio Devices], IPortClsNotifications interface [Audio Devices],described, audio.iportclsnotifications, portcls/IPortClsNotifications
req.header: portcls.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Available in Windows 10, version 1703 and later versions of Windows.
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
targetos: Windows
req.typenames: 
f1_keywords:
 - IPortClsNotifications
 - portcls/IPortClsNotifications
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - portcls.h
api_name:
 - IPortClsNotifications
---

# IPortClsNotifications interface


## -description

An interface implemented by ports to provide
 notification helpers to miniports to support audio module communication.

For more information about audio modules, 
 see <a href="/windows-hardware/drivers/audio/implementing-audio-module-communication">Implementing Audio Module Discovery</a>. 
 

The miniport audio driver will call into their port to create and send the notification.

## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IPortClsNotifications</b> interface inherits from the <a href="/windows/win32/api/unknwn/nn-unknwn-iunknown">IUnknown</a> interface. <b>IPortClsNotifications</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>