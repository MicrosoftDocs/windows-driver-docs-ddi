---
UID: NE:storport.STOR_PNP_ACTION
tech.root: storage
title: STOR_PNP_ACTION (storport.h)
ms.date: 07/25/2024
targetos: Windows
description: Learn more about the STOR_PNP_ACTION enumeration.
prerelease: false
req.construct-type: enumeration
req.ddi-compliance: 
req.header: storport.h
req.include-header: 
req.kmdf-ver: 
req.max-support: 
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: 
req.target-type: 
req.typenames: 
typedef_isUnnamed: true
req.umdf-ver: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - storport.h
api_name:
 - STOR_PNP_ACTION
 - PSTOR_PNP_ACTION
f1_keywords:
 - STOR_PNP_ACTION
 - storport/STOR_PNP_ACTION
 - PSTOR_PNP_ACTION
 - storport/PSTOR_PNP_ACTION
dev_langs:
 - c++
helpviewer_keywords:
 - STOR_PNP_ACTION
---

## -description

See [**STOR_PNP_ACTION** (*srb.h*)](../srb/ne-srb-stor_pnp_action.md).

## -enum-fields

### -field StorStartDevice:0x0

### -field StorRemoveDevice:0x2

### -field StorStopDevice:0x4

### -field StorQueryCapabilities:0x9

### -field StorQueryResourceRequirements:0xB

### -field StorFilterResourceRequirements:0xD

### -field StorSurpriseRemoval:0x17

## -see-also

[**SCSI_PNP_REQUEST_BLOCK**](../srb/ns-srb-_scsi_pnp_request_block.md)

[**SRBEX_DATA_PNP**](../srb/ns-srb-_srbex_data_pnp.md)
