---
UID: NN:portcls.IDrmPort
title: IDrmPort
description: The IDrmPort interface is used by a WaveCyclic or WavePci miniport driver to manage DRM-protected content (see Digital Rights Management).
old-location: audio\idrmport.htm
tech.root: audio
ms.assetid: 3a4b9bf7-74cc-409f-9b63-db61d7c977cd
ms.date: 03/19/2018
ms.keywords: IDrmPort, IDrmPort interface [Audio Devices], IDrmPort interface [Audio Devices], described, audio.idrmport, audmp-routines_c68e5cec-890e-48c8-8d1c-443b521e5477.xml, portcls/IDrmPort
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
-	IDrmPort
product:
- Windows
targetos: Windows
req.typenames: PC_EXIT_LATENCY, *PPC_EXIT_LATENCY
---

# IDrmPort interface


## -description


The <code>IDrmPort</code> interface is used by a WaveCyclic or WavePci miniport driver to manage DRM-protected content (see <a href="https://msdn.microsoft.com/7ce19196-5180-421f-b6be-ac4a235a8c16">Digital Rights Management</a>). The port driver implements this interface and exposes it to the miniport driver. In Windows XP and later, the WaveCyclic and WavePci port drivers support this interface. To determine whether a port driver supports the <code>IDrmPort</code> interface, a miniport driver calls the port (<a href="https://msdn.microsoft.com/library/windows/hardware/ff536899">IPortWaveCyclic</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff536905">IPortWavePci</a>) object's <b>QueryInterface</b> method with REFIID <b>IID_IDrmPort</b>.

The methods in this interface serve as alternate entry points to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff536356">DRM Functions</a> in the <a href="https://msdn.microsoft.com/827997e2-6f07-4635-ac35-4ad026b82eae">DRMK system driver</a>, drmk.sys.

For more information about <code>IDrmPort</code>, see <a href="https://msdn.microsoft.com/aee123e4-bc1b-4ba8-9f8d-a9d207297c8d">Content IDs and Content Rights</a>.

