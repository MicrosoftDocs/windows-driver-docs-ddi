---
UID: NS:avc._AVC_SUBUNIT_INFO_BLOCK
title: _AVC_SUBUNIT_INFO_BLOCK (avc.h)
description: The AVC_SUBUNIT_INFO_BLOCK structure describes subunit information.
old-location: stream\avc_subunit_info_block.htm
tech.root: stream
ms.date: 04/23/2018
keywords: ["AVC_SUBUNIT_INFO_BLOCK structure"]
ms.keywords: "*PAVC_SUBUNIT_INFO_BLOCK, AVC_SUBUNIT_INFO_BLOCK, AVC_SUBUNIT_INFO_BLOCK structure [Streaming Media Devices], PAVC_SUBUNIT_INFO_BLOCK, PAVC_SUBUNIT_INFO_BLOCK structure pointer [Streaming Media Devices], _AVC_SUBUNIT_INFO_BLOCK, avc/AVC_SUBUNIT_INFO_BLOCK, avc/PAVC_SUBUNIT_INFO_BLOCK, avcref_d8151f14-0fc4-4be5-b815-d94dc77165db.xml, stream.avc_subunit_info_block"
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
req.typenames: AVC_SUBUNIT_INFO_BLOCK, *PAVC_SUBUNIT_INFO_BLOCK
f1_keywords:
 - _AVC_SUBUNIT_INFO_BLOCK
 - avc/_AVC_SUBUNIT_INFO_BLOCK
 - PAVC_SUBUNIT_INFO_BLOCK
 - avc/PAVC_SUBUNIT_INFO_BLOCK
 - AVC_SUBUNIT_INFO_BLOCK
 - avc/AVC_SUBUNIT_INFO_BLOCK
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - avc.h
api_name:
 - _AVC_SUBUNIT_INFO_BLOCK
 - PAVC_SUBUNIT_INFO_BLOCK
 - AVC_SUBUNIT_INFO_BLOCK
---

# _AVC_SUBUNIT_INFO_BLOCK structure


## -description

The AVC_SUBUNIT_INFO_BLOCK structure describes subunit information.

## -struct-fields

### -field Info

Ignored on input. On output, this contains up to eight contiguous pages of subunit information in the format of the AV/C SUBUNIT_INFO unit command. The subunit information pages are terminated with 0xff. See Section 9.11 of the AV/C Digital Interface Command Set General Specification, Rev 3.0.

## -remarks

This structure is used with the <a href="/windows-hardware/drivers/stream/avc-function-get-subunit-info">AVC_FUNCTION_GET_SUBUNIT_INFO</a> function code.

This structure is used only as a member inside the AVC_MULTIFUNC_IRB structure. It is not used by itself.

See <a href="/windows-hardware/drivers/stream/using-avc-sys">How to Use Avc.sys</a> For information about building and sending an AV/C command.

## -see-also

<a href="/windows-hardware/drivers/ddi/avc/ne-avc-_tagavc_function">AVC_FUNCTION</a>



<a href="/windows-hardware/drivers/stream/avc-function-get-subunit-info">AVC_FUNCTION_GET_SUBUNIT_INFO</a>



<a href="/windows-hardware/drivers/ddi/avc/ns-avc-_avc_multifunc_irb">AVC_MULTIFUNC_IRB</a>

