---
UID: NS:avc._AVC_PEER_DO_LIST
title: _AVC_PEER_DO_LIST (avc.h)
description: The AVC_PEER_DO_LIST describes all nonvirtual (peer) instances of avc.sys.
old-location: stream\avc_peer_do_list.htm
tech.root: stream
ms.date: 04/23/2018
keywords: ["AVC_PEER_DO_LIST structure"]
ms.keywords: "*PAVC_PEER_DO_LIST, AVC_PEER_DO_LIST, AVC_PEER_DO_LIST structure [Streaming Media Devices], PAVC_PEER_DO_LIST, PAVC_PEER_DO_LIST structure pointer [Streaming Media Devices], _AVC_PEER_DO_LIST, avc/AVC_PEER_DO_LIST, avc/PAVC_PEER_DO_LIST, avcref_69feff07-d80c-4d5a-a5d8-fe942dfc5e26.xml, stream.avc_peer_do_list"
req.header: avc.h
req.include-header: Avc.h
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
req.typenames: AVC_PEER_DO_LIST, *PAVC_PEER_DO_LIST
f1_keywords:
 - _AVC_PEER_DO_LIST
 - avc/_AVC_PEER_DO_LIST
 - PAVC_PEER_DO_LIST
 - avc/PAVC_PEER_DO_LIST
 - AVC_PEER_DO_LIST
 - avc/AVC_PEER_DO_LIST
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - avc.h
api_name:
 - AVC_PEER_DO_LIST
---

# _AVC_PEER_DO_LIST structure


## -description

The AVC_PEER_DO_LIST describes all nonvirtual (peer) instances of <i>avc.sys</i>.

## -struct-fields

### -field Count

Ignored on input. On output, set to the number of objects in the list. If zero, the caller must not attempt to dereference the <b>Objects</b> member (it is set to <b>NULL</b>).

### -field Objects

Ignored on input. On output (and if the <b>Count</b> member is not zero) <b>Objects</b> contains a pointer to a contiguous array of DEVICE_OBJECT pointers. The caller must release the reference held on each object (by using <b>ObDereferenceObject</b>), and free the memory containing the list (by using <b>ExFreePool</b>) when finished with it.

## -remarks

This structure is used with the <a href="/windows-hardware/drivers/stream/avc-function-peer-do-list">AVC_FUNCTION_PEER_DO_LIST</a> function code.

This structure is used only as a member inside the AVC_MULTIFUNC_IRB structure. It is not used by itself.

See <a href="/windows-hardware/drivers/stream/using-avc-sys">How to Use Avc.sys</a> For information about building and sending an AV/C command.

## -see-also

<a href="/windows-hardware/drivers/ddi/avc/ne-avc-_tagavc_function">AVC_FUNCTION</a>



<a href="/windows-hardware/drivers/stream/avc-function-peer-do-list">AVC_FUNCTION_PEER_DO_LIST</a>



<a href="/windows-hardware/drivers/ddi/avc/ns-avc-_avc_multifunc_irb">AVC_MULTIFUNC_IRB</a>
