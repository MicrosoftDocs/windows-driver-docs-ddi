---
UID: NS:hidpi._HIDP_LINK_COLLECTION_NODE
title: _HIDP_LINK_COLLECTION_NODE (hidpi.h)
description: The HIDP_LINK_COLLECTION_NODE structure contains information about a link collection in a top-level collection's link collection array.
old-location: hid\hidp_link_collection_node.htm
tech.root: hid
ms.date: 04/30/2018
keywords: ["HIDP_LINK_COLLECTION_NODE structure"]
ms.keywords: "*PHIDP_LINK_COLLECTION_NODE, HIDP_LINK_COLLECTION_NODE, HIDP_LINK_COLLECTION_NODE structure [Human Input Devices], PHIDP_LINK_COLLECTION_NODE, PHIDP_LINK_COLLECTION_NODE structure pointer [Human Input Devices], _HIDP_LINK_COLLECTION_NODE, hid.hidp_link_collection_node, hidpi/HIDP_LINK_COLLECTION_NODE, hidpi/PHIDP_LINK_COLLECTION_NODE, hidstrct_8d1c79e1-c19d-4896-9572-cae49a06304a.xml"
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
req.irql: 
targetos: Windows
req.typenames: HIDP_LINK_COLLECTION_NODE, *PHIDP_LINK_COLLECTION_NODE
f1_keywords:
 - _HIDP_LINK_COLLECTION_NODE
 - hidpi/_HIDP_LINK_COLLECTION_NODE
 - PHIDP_LINK_COLLECTION_NODE
 - hidpi/PHIDP_LINK_COLLECTION_NODE
 - HIDP_LINK_COLLECTION_NODE
 - hidpi/HIDP_LINK_COLLECTION_NODE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - hidpi.h
api_name:
 - _HIDP_LINK_COLLECTION_NODE
 - PHIDP_LINK_COLLECTION_NODE
 - HIDP_LINK_COLLECTION_NODE
---

# _HIDP_LINK_COLLECTION_NODE structure


## -description

The HIDP_LINK_COLLECTION_NODE structure contains information about a <a href="/windows-hardware/drivers/hid/link-collections">link collection</a> in a <a href="/windows-hardware/drivers/hid/top-level-collections">top-level collection's</a> <a href="/windows-hardware/drivers/hid/link-collections">link collection array</a>.

## -struct-fields

### -field LinkUsage

Specifies the <a href="/windows-hardware/drivers/hid/hid-usages">usage ID</a> of a top-level collection.

### -field LinkUsagePage

Specifies the <a href="/windows-hardware/drivers/hid/hid-usages">usage page</a> of the collection.

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

Specifies, if <b>TRUE</b>, that this collection is an <a href="/windows-hardware/drivers/hid/link-collections">aliased collection</a>. Otherwise, if <b>FALSE</b>, the collection is not aliased.

### -field Reserved

Reserved for internal system use.

### -field UserContext

Pointer to application-specific information.

## -remarks

The <a href="/windows-hardware/drivers/ddi/hidpi/nf-hidpi-hidp_getlinkcollectionnodes">HidP_GetLinkCollectionNodes</a> routine returns a top-level collection's link collection array. The indices specified in a link collection node are indices in the collection's link collection array.

## -see-also

<a href="/windows-hardware/drivers/ddi/hidpi/ns-hidpi-_hidp_button_caps">HIDP_BUTTON_CAPS</a>



<a href="/windows-hardware/drivers/ddi/hidpi/ns-hidpi-_hidp_value_caps">HIDP_VALUE_CAPS</a>



<a href="/windows-hardware/drivers/ddi/hidpi/nf-hidpi-hidp_getlinkcollectionnodes">HidP_GetLinkCollectionNodes</a>

