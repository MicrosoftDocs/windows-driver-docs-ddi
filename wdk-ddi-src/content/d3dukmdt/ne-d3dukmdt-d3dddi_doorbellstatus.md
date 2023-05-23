---
UID: NE:d3dukmdt._D3DDDI_DOORBELLSTATUS
tech.root: display
title: D3DDDI_DOORBELLSTATUS
ms.date: 05/22/2023
targetos: Windows
description: Learn more about the D3DDDI_DOORBELLSTATUS structure.
prerelease: true
req.construct-type: enumeration
req.ddi-compliance: 
req.header: d3dukmdt.h
req.include-header: 
req.kmdf-ver: 
req.max-support: 
req.target-min-winverclnt: WIN11_FUTURE
req.target-min-winversvr: 
req.target-type: 
req.typenames: 
typedef_isUnnamed: false
req.umdf-ver: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3dukmdt.h
api_name:
 - _D3DDDI_DOORBELLSTATUS
 - D3DDDI_DOORBELLSTATUS
f1_keywords:
 - _D3DDDI_DOORBELLSTATUS
 - d3dukmdt/_D3DDDI_DOORBELLSTATUS
 - D3DDDI_DOORBELLSTATUS
 - d3dukmdt/D3DDDI_DOORBELLSTATUS
dev_langs:
 - c++
helpviewer_keywords:
 - _D3DDDI_DOORBELLSTATUS
---

## -description

The **D3DDDI_DOORBELLSTATUS** enumeration indicates the status of a doorbell object.

## -enum-fields

### -field D3DDDI_DOORBELLSTATUS_CONNECTED

Indicates that the doorbell object is successfully connected to a hardware queue and ready for work submission.

### -field D3DDDI_DOORBELLSTATUS_CONNECTED_NOTIFY_KMD

Indicates that the doorbell object is connected; however, UMD should [notify KMD](../d3dkmddi/nc-d3dkmddi-dxgkddi_notifyworksubmission.md) after every new work submission and doorbell ring.

### -field D3DDDI_DOORBELLSTATUS_DISCONNECTED_RETRY

Indicates that the doorbell can't be connected at this time; however, UMD should retry to connect it.

### -field D3DDDI_DOORBELLSTATUS_DISCONNECTED_ABORT

Indicates that the doorbell won't be connected and UMD can't use this hardware queue for work submission. This failure typically implies a nonrecoverable scenario such as a GPU reset or stopped adapter.

## -see-also

[**DXGKARG_CONNECTDOORBELL**](ns-d3dkmddi-dxgkarg_connectdoorbell.md)

[**DXGKARG_DISCONNECTDOORBELL**](ns-d3dkmddi-dxgkarg_disconnectdoorbell.md)

[**DxgkDdiConnectDoorbell**](nc-d3dkmddi-dxgkddi_connectdoorbell.md)

[**DxgkDdiDisconnectDoorbell**](nc-d3dkmddi-dxgkddi_disconnectdoorbell.md)
