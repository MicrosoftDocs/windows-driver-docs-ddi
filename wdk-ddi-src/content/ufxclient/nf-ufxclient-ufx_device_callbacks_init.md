---
UID: NF:ufxclient.UFX_DEVICE_CALLBACKS_INIT
title: UFX_DEVICE_CALLBACKS_INIT function (ufxclient.h)
description: The UFX_DEVICE_CALLBACKS_INIT macro initializes the UFX_DEVICE_CALLBACKS structure.
old-location: buses\ufx_device_callbacks_init.htm
tech.root: usbref
ms.date: 05/07/2018
keywords: ["UFX_DEVICE_CALLBACKS_INIT function"]
ms.keywords: UFX_DEVICE_CALLBACKS_INIT, UFX_DEVICE_CALLBACKS_INIT function [Buses], buses.ufx_device_callbacks_init, ufxclient/UFX_DEVICE_CALLBACKS_INIT
req.header: ufxclient.h
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
req.lib: ufxstub.lib
req.dll: 
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - UFX_DEVICE_CALLBACKS_INIT
 - ufxclient/UFX_DEVICE_CALLBACKS_INIT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ufxclient.h
api_name:
 - UFX_DEVICE_CALLBACKS_INIT
---

# UFX_DEVICE_CALLBACKS_INIT function


## -description

The <b>UFX_DEVICE_CALLBACKS_INIT</b> macro initializes the <a href="/windows-hardware/drivers/ddi/ufxclient/ns-ufxclient-_ufx_device_callbacks">UFX_DEVICE_CALLBACKS</a> structure.

## -parameters

### -param Callbacks 

[out]
A pointer to the <a href="/windows-hardware/drivers/ddi/ufxclient/ns-ufxclient-_ufx_device_callbacks">UFX_DEVICE_CALLBACKS</a> structure.

## -remarks

The <b>UFX_DEVICE_CALLBACKS_INIT</b> macro will set all fields of the <a href="/windows-hardware/drivers/ddi/ufxclient/ns-ufxclient-_ufx_device_callbacks">UFX_DEVICE_CALLBACKS</a> structure to zero and set the <b>Size</b> field appropriately.

The client driver uses the <b>UFX_DEVICE_CALLBACKS_INIT</b> macro the initialize the <a href="/windows-hardware/drivers/ddi/ufxclient/ns-ufxclient-_ufx_device_callbacks">UFX_DEVICE_CALLBACKS</a> structure prior to calling <a href="/windows-hardware/drivers/ddi/ufxclient/nf-ufxclient-ufxdevicecreate">UfxDeviceCreate</a>.
