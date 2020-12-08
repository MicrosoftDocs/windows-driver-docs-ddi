---
UID: NF:storport.StorPortWriteRegisterBufferUchar
title: StorPortWriteRegisterBufferUchar macro (storport.h)
description: The StorPortWriteRegisterBufferUchar routine transfers a given number of unsigned bytes from a buffer to the HBA.
old-location: storage\storportwriteregisterbufferuchar.htm
tech.root: storage
ms.date: 03/29/2018
keywords: ["StorPortWriteRegisterBufferUchar macro"]
ms.keywords: StorPortWriteRegisterBufferUchar, StorPortWriteRegisterBufferUchar routine [Storage Devices], storage.storportwriteregisterbufferuchar, storport/StorPortWriteRegisterBufferUchar, storprt_21fa4636-6492-4cb1-9281-6f116f1a7591.xml
req.header: storport.h
req.include-header: Storport.h
req.target-type: Universal
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
req.lib: Storport.lib
req.dll: 
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - StorPortWriteRegisterBufferUchar
 - storport/StorPortWriteRegisterBufferUchar
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Storport.lib
 - Storport.dll
api_name:
 - StorPortWriteRegisterBufferUchar
---

# StorPortWriteRegisterBufferUchar macro


## -description

The <b>StorPortWriteRegisterBufferUchar</b> routine transfers a given number of unsigned bytes from a buffer to the HBA.

## -parameters

### -param h

<p>A pointer to the hardware device extension. This is a per HBA storage area that the port driver allocates and initializes on behalf of the miniport driver. Miniport drivers usually store HBA-specific information in this extension, such as the state of the HBA and the mapped access ranges for the HBA. This area is available to the miniport driver immediately after the miniport driver calls <a href="/windows-hardware/drivers/ddi/storport/nf-storport-storportinitialize"><b>StorPortInitialize</b></a>. The port driver frees this memory when it removes the device. </p>

### -param r

Pointer to the register. The given <i>Register</i> must be in a mapped memory-space range returned by [**StorPortGetDeviceBase**](nf-storport-storportgetdevicebase.md).

### -param b

<p>Pointer to a buffer containing the data to be written. </p>

### -param c

<p>Specifies the number of bytes to be transferred to the HBA. </p>

## -see-also

<a href="/windows-hardware/drivers/ddi/srb/nf-srb-scsiportwriteregisterbufferuchar">ScsiPortWriteRegisterBufferUchar</a>
