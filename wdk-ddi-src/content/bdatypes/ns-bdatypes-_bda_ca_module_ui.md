---
UID: NS:bdatypes._BDA_CA_MODULE_UI
title: "_BDA_CA_MODULE_UI"
author: windows-driver-content
description: The BDA_CA_MODULE_UI structure describes the user interface (UI) that conditional access (CA) plugins can display.
old-location: stream\bda_ca_module_ui.htm
old-project: stream
ms.assetid: 2f2c8cb5-0e84-467f-9671-735575835c3a
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: PBDA_CA_MODULE_UI structure pointer [Streaming Media Devices], *PBDA_CA_MODULE_UI, BDA_CA_MODULE_UI structure [Streaming Media Devices], stream.bda_ca_module_ui, PBDA_CA_MODULE_UI, BDA_CA_MODULE_UI, bdatypes/BDA_CA_MODULE_UI, bdaref_470f210b-d1cb-4615-a7c5-a4d8e21833d1.xml, bdatypes/PBDA_CA_MODULE_UI, _BDA_CA_MODULE_UI
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	bdatypes.h
apiname:
-	BDA_CA_MODULE_UI
product: Windows
targetos: Windows
req.typenames: "*PBDA_CA_MODULE_UI, BDA_CA_MODULE_UI"
---

# _BDA_CA_MODULE_UI structure


## -description


The BDA_CA_MODULE_UI structure describes the user interface (UI) that conditional access (CA) plugins can display. 


## -syntax


````
typedef struct _BDA_CA_MODULE_UI {
  ULONG ulFormat;
  ULONG ulbcDesc;
  ULONG ulDesc[MIN_DIMENSION];
} BDA_CA_MODULE_UI, *PBDA_CA_MODULE_UI;
````


## -struct-fields




### -field ulFormat

Value that specifies the format of the UI. 


### -field ulbcDesc

Number of descriptors in the <b>ulDesc</b> array. 


### -field ulDesc

Array of descriptors for the UI. 


## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff566536">KSPROPSETID_BdaCA</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564294">KSPROPERTY_BDA_CA_MODULE_UI</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20BDA_CA_MODULE_UI structure%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

