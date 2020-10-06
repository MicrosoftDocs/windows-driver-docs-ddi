---
UID: NF:storport.StorPortWriteRegisterUchar
title: StorPortWriteRegisterUchar macro (storport.h)
description: The StorPortWriteRegisterBufferUshort routine transfers a given number of character values from a buffer to the indicated HBA register address.
old-location: storage\storportwriteregisteruchar.htm
tech.root: storage
ms.assetid: 731ae55e-8cfb-4b76-b811-dbdabd8dd067
ms.date: 03/29/2018
keywords: ["StorPortWriteRegisterUchar macro"]
ms.keywords: StorPortWriteRegisterUchar, StorPortWriteRegisterUchar routine [Storage Devices], storage.storportwriteregisteruchar, storport/StorPortWriteRegisterUchar, storprt_5c7a4209-e917-4a68-94f7-7b3b3fcc634e.xml
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
 - StorPortWriteRegisterUchar
 - storport/StorPortWriteRegisterUchar
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Storport.lib
 - Storport.dll
api_name:
 - StorPortWriteRegisterUchar
---

# StorPortWriteRegisterUchar macro


## -description

The <b>StorPortWriteRegisterBufferUshort</b> routine transfers a given number of character values from a buffer to the indicated HBA register address.

## -parameters

### -param h

<p>A pointer to the hardware device extension. This is a per HBA storage area that the port driver allocates and initializes on behalf of the miniport driver. Miniport drivers usually store HBA-specific information in this extension, such as the state of the HBA and the mapped access ranges for the HBA. This area is available to the miniport driver immediately after the miniport driver calls <a href="/windows-hardware/drivers/ddi/storport/nf-storport-storportinitialize"><b>StorPortInitialize</b></a>. The port driver frees this memory when it removes the device. </p>

### -param r

<p>Pointer to the register. The given <i>Register</i> must be in a mapped memory space range returned by <a href="/windows-hardware/drivers/ddi/storport/nf-storport-storportgetdevicebase"><b>StorPortGetDeviceBase</b></a>. </p>

### -param v

<p>Specifies the value to be written to the HBA's register.</p>

## -see-also

<a href="/windows-hardware/drivers/ddi/srb/nf-srb-scsiportwriteregisterbufferushort">ScsiPortWriteRegisterBufferUshort</a>