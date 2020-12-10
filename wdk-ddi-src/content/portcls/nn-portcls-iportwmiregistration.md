---
UID: NN:portcls.IPortWMIRegistration
title: IPortWMIRegistration (portcls.h)
description: The IPortWMIRegistration interface is provided in Windows 7 and later versions of Windows. This interface allows the miniport driver to coordinate Event Tracing for Windows (ETW) registration between PortCls and the miniport driver.
old-location: audio\iportwmiregistration.htm
tech.root: audio
ms.date: 05/08/2018
keywords: ["IPortWMIRegistration interface"]
ms.keywords: IPortWMIRegistration, IPortWMIRegistration interface [Audio Devices], IPortWMIRegistration interface [Audio Devices],described, audio.iportwmiregistration, audmp-routines_c7591b25-80f3-4d0e-ac6b-bc1dea55adb1.xml, portcls/IPortWMIRegistration
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
targetos: Windows
req.typenames: 
f1_keywords:
 - IPortWMIRegistration
 - portcls/IPortWMIRegistration
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - portcls.h
api_name:
 - IPortWMIRegistration
---

# IPortWMIRegistration interface


## -description

The <code>IPortWMIRegistration</code> interface is provided in Windows 7 and later versions of Windows. This interface allows the miniport driver to coordinate Event Tracing for Windows (ETW) registration between PortCls and the miniport driver.

ETW provides a mechanism to trace and log events that are raised by user-mode applications and kernel-mode drivers. For more information about ETW, see <a href="/windows-hardware/test/wpt/event-tracing-for-windows">Event Tracing for Windows</a> and <a href="/archive/msdn-magazine/2007/april/event-tracing-improve-debugging-and-performance-tuning-with-etw">Improve Debugging And Performance Tuning With ETW</a>.

## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IPortWMIRegistration</b> interface inherits from the <a href="/windows/win32/api/unknwn/nn-unknwn-iunknown">IUnknown</a> interface. <b>IPortWMIRegistration</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>
