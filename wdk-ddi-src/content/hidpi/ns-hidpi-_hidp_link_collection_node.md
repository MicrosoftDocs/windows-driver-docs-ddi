---
UID: NS:hidpi._HIDP_LINK_COLLECTION_NODE
title: "_HIDP_LINK_COLLECTION_NODE"
author: windows-driver-content
description: The HIDP_LINK_COLLECTION_NODE structure contains information about a link collection in a top-level collection's link collection array.
old-location: hid\hidp_link_collection_node.htm
old-project: hid
ms.assetid: 66ffd219-4a62-404d-ba51-4a91eccfcf96
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: "*PHIDP_LINK_COLLECTION_NODE, HIDP_LINK_COLLECTION_NODE, HIDP_LINK_COLLECTION_NODE structure [Human Input Devices], PHIDP_LINK_COLLECTION_NODE, PHIDP_LINK_COLLECTION_NODE structure pointer [Human Input Devices], _HIDP_LINK_COLLECTION_NODE, hid.hidp_link_collection_node, hidpi/HIDP_LINK_COLLECTION_NODE, hidpi/PHIDP_LINK_COLLECTION_NODE, hidstrct_8d1c79e1-c19d-4896-9572-cae49a06304a.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: hidpi.h
req.include-header: Hidpi.h
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	hidpi.h
api_name:
-	HIDP_LINK_COLLECTION_NODE
product:
- Windows
targetos: Windows
req.typenames: HIDP_LINK_COLLECTION_NODE, *PHIDP_LINK_COLLECTION_NODE
---

# _HIDP_LINK_COLLECTION_NODE structure


## -description


The HIDP_LINK_COLLECTION_NODE structure contains information about a <a href="https://msdn.microsoft.com/3f934661-c33c-4c08-82ac-ee2e0f519c8e">link collection</a> in a <a href="https://msdn.microsoft.com/dcbee8e3-d03a-45c8-92e4-0897b9f55177">top-level collection's</a> <a href="https://msdn.microsoft.com/3f934661-c33c-4c08-82ac-ee2e0f519c8e">link collection array</a>.


## -struct-fields




### -field LinkUsage

Specifies the <a href="https://msdn.microsoft.com/84fed314-3554-4291-b51c-734d874a4bab">usage ID</a> of a top-level collection.


### -field LinkUsagePage

Specifies the <a href="https://msdn.microsoft.com/84fed314-3554-4291-b51c-734d874a4bab">usage page</a> of the collection.


### -field Parent

Specifies the index of the collection's parent collection. If the collection has no parent, <b>Parent</b> is zero.


### -field NumberOfChildren

Specifies the number of child collections that the collection contains.


### -field NextSibling

Specifies the index of the collection's immediate sibling. If the collection has no sibling, <b>NextSibling</b> is zero.


### -field FirstChild

Specifies the index of the collection's first child collection. If the collection has no children, <b>FirstChild</b> is zero.


### -field CollectionType

Specifies the type of collection item.


### -field IsAlias

Specifies, if <b>TRUE</b>, that this collection is an <a href="https://msdn.microsoft.com/3f934661-c33c-4c08-82ac-ee2e0f519c8e">aliased collection</a>. Otherwise, if <b>FALSE</b>, the collection is not aliased.


### -field Reserved

Reserved for internal system use.


### -field UserContext

Pointer to application-specific information.


## -remarks



The <a href="https://msdn.microsoft.com/library/windows/hardware/ff539725">HidP_GetLinkCollectionNodes</a> routine returns a top-level collection's link collection array. The indices specified in a link collection node are indices in the collection's link collection array.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff539693">HIDP_BUTTON_CAPS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff539832">HIDP_VALUE_CAPS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff539725">HidP_GetLinkCollectionNodes</a>
 

 

