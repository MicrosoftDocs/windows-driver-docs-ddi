---
UID: NN:portcls.IPreFetchOffset
title: IPreFetchOffset (portcls.h)
description: The IPreFetchOffset interface controls the prefetch offset, which is the number of bytes separating the play and write cursors in a DirectSound output stream.
old-location: audio\iprefetchoffset.htm
tech.root: audio
ms.assetid: 8c6a3766-c959-4979-8dc9-3b5234003272
ms.date: 05/08/2018
keywords: ["IPreFetchOffset interface"]
ms.keywords: IPreFetchOffset, IPreFetchOffset interface [Audio Devices], IPreFetchOffset interface [Audio Devices],described, audio.iprefetchoffset, audmp-routines_71e52125-c3a2-4434-96f3-e3a66b482a3a.xml, portcls/IPreFetchOffset
f1_keywords:
 - "portcls/IPreFetchOffset"
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
- IPreFetchOffset
product:
- Windows
targetos: Windows
req.typenames: 
---

# IPreFetchOffset interface


## -description


The <code>IPreFetchOffset</code> interface controls the prefetch offset, which is the number of bytes separating the play and write cursors in a DirectSound output stream. A WavePci miniport driver can use this interface to prevent the prefetch offset from growing too large when the driver allocates a large number of mappings. This interface is supported only in Windows XP and later. To determine whether the WavePci port driver supports the <code>IPreFetchOffset</code> interface, a miniport driver calls the port stream (<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nn-portcls-iportwavepcistream">IPortWavePciStream</a>) object's <b>QueryInterface</b> method with REFIID <b>IID_IPreFetchOffset</b>. 

For more information about the <code>IPreFetchOffset</code> interface, see <a href="https://docs.microsoft.com/windows-hardware/drivers/audio/prefetch-offsets">Prefetch Offsets</a>.


## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IPreFetchOffset</b> interface inherits from the <a href="https://docs.microsoft.com/windows/win32/api/unknwn/nn-unknwn-iunknown">IUnknown</a> interface. <b>IPreFetchOffset</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

