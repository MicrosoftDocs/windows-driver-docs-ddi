---
UID: NS:bdatypes._BDA_CA_MODULE_UI
title: _BDA_CA_MODULE_UI (bdatypes.h)
description: The BDA_CA_MODULE_UI structure describes the user interface (UI) that conditional access (CA) plugins can display.
old-location: stream\bda_ca_module_ui.htm
tech.root: stream
ms.date: 04/23/2018
keywords: ["BDA_CA_MODULE_UI structure"]
ms.keywords: "*PBDA_CA_MODULE_UI, BDA_CA_MODULE_UI, BDA_CA_MODULE_UI structure [Streaming Media Devices], PBDA_CA_MODULE_UI, PBDA_CA_MODULE_UI structure pointer [Streaming Media Devices], _BDA_CA_MODULE_UI, bdaref_470f210b-d1cb-4615-a7c5-a4d8e21833d1.xml, bdatypes/BDA_CA_MODULE_UI, bdatypes/PBDA_CA_MODULE_UI, stream.bda_ca_module_ui"
req.header: bdatypes.h
req.include-header: Bdatypes.h
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
req.typenames: BDA_CA_MODULE_UI, *PBDA_CA_MODULE_UI
f1_keywords:
 - _BDA_CA_MODULE_UI
 - bdatypes/_BDA_CA_MODULE_UI
 - PBDA_CA_MODULE_UI
 - bdatypes/PBDA_CA_MODULE_UI
 - BDA_CA_MODULE_UI
 - bdatypes/BDA_CA_MODULE_UI
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - bdatypes.h
api_name:
 - BDA_CA_MODULE_UI
---

# _BDA_CA_MODULE_UI structure


## -description

The BDA_CA_MODULE_UI structure describes the user interface (UI) that conditional access (CA) plugins can display.

## -struct-fields

### -field ulFormat

Value that specifies the format of the UI.

### -field ulbcDesc

Number of descriptors in the <b>ulDesc</b> array.

### -field ulDesc

Array of descriptors for the UI.

## -see-also

<a href="/windows-hardware/drivers/stream/ksproperty-bda-ca-module-ui">KSPROPERTY_BDA_CA_MODULE_UI</a>



<a href="/windows-hardware/drivers/stream/kspropsetid-bdaca">KSPROPSETID_BdaCA</a>
