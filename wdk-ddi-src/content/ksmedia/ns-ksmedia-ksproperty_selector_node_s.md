---
UID: NS:ksmedia.KSPROPERTY_SELECTOR_NODE_S
title: KSPROPERTY_SELECTOR_NODE_S
author: windows-driver-content
description: The KSPROPERTY_SELECTOR_NODE_S structure describes node-based property settings in the PROPSETID_VIDCAP_SELECTOR property set.
old-location: stream\ksproperty_selector_node_s.htm
old-project: stream
ms.assetid: 37dc9f4a-1e9c-42f2-8894-4972562f5898
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: PKSPROPERTY_SELECTOR_NODE_S, KSPROPERTY_SELECTOR_NODE_S structure [Streaming Media Devices], *PKSPROPERTY_SELECTOR_NODE_S, ksmedia/KSPROPERTY_SELECTOR_NODE_S, vidcapstruct_f7f566f9-2eea-44f5-8a4b-33769d99576f.xml, KSPROPERTY_SELECTOR_NODE_S, PKSPROPERTY_SELECTOR_NODE_S structure pointer [Streaming Media Devices], ksmedia/PKSPROPERTY_SELECTOR_NODE_S, stream.ksproperty_selector_node_s
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ksmedia.h
req.include-header: Ksmedia.h
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ksmedia.h
apiname:
-	KSPROPERTY_SELECTOR_NODE_S
product: Windows
targetos: Windows
req.typenames: KSPROPERTY_SELECTOR_NODE_S, *PKSPROPERTY_SELECTOR_NODE_S
---

# KSPROPERTY_SELECTOR_NODE_S structure


## -description


The KSPROPERTY_SELECTOR_NODE_S structure describes node-based property settings in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff567810">PROPSETID_VIDCAP_SELECTOR</a> property set.


## -syntax


````
typedef struct {
  KSP_NODE NodeProperty;
  LONG     Value;
  ULONG    Flags;
  ULONG    Capabilities;
} KSPROPERTY_SELECTOR_NODE_S, *PKSPROPERTY_SELECTOR_NODE_S;
````


## -struct-fields




#### - NodeProperty

Specifies an initialized <a href="..\ks\ns-ks-ksp_node.md">KSP_NODE</a> structure that describes the node, property set, property ID, and request type.


#### - Value

Specifies the value of a request. For Set requests, the minidriver should set the property specified in <b>Property</b> to this value. For Get requests, the minidriver should return the value of the property specified in <b>Property</b>.


#### - Flags

Specifies the flags of a request. For Set requests, this value indicates the desired setting. For Get requests, this value contains the current setting.


#### - Capabilities

Specifies the capabilities of a property. This member has meaning only for Get requests. The minidriver should return the capabilities of the Selector with respect to the property specified in <b>Property</b>.


## -see-also

<a href="..\ksmedia\ns-ksmedia-ksproperty_selector_s.md">KSPROPERTY_SELECTOR_S</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KSPROPERTY_SELECTOR_NODE_S structure%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

