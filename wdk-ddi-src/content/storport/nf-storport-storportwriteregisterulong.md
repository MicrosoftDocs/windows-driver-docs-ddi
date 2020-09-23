---
UID: NF:storport.StorPortWriteRegisterUlong
title: StorPortWriteRegisterUlong macro (storport.h)
description: The StorPortWriteRegisterUlong routine transfers a ULONG value to the indicated HBA register address.
old-location: storage\storportwriteregisterulong.htm
tech.root: storage
ms.assetid: 12ed5f88-26af-43a4-82c7-5f36d9388cc8
ms.date: 03/29/2018
keywords: ["StorPortWriteRegisterUlong macro"]
ms.keywords: StorPortWriteRegisterUlong, StorPortWriteRegisterUlong routine [Storage Devices], storage.storportwriteregisterulong, storport/StorPortWriteRegisterUlong, storprt_64890de0-32e7-4e07-bcbc-35a11acd6896.xml
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
 - StorPortWriteRegisterUlong
 - storport/StorPortWriteRegisterUlong
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Storport.lib
 - Storport.dll
api_name:
 - StorPortWriteRegisterUlong
---

# StorPortWriteRegisterUlong macro


## -description

The <b>StorPortWriteRegisterUlong</b> routine transfers a ULONG value to the indicated HBA register address.

## -parameters

### -param h

<p>A pointer to the hardware device extension. This is a per HBA storage area that the port driver allocates and initializes on behalf of the miniport driver. Miniport drivers usually store HBA-specific information in this extension, such as the state of the HBA and the mapped access ranges for the HBA. This area is available to the miniport driver immediately after the miniport driver calls <a href="/windows-hardware/drivers/ddi/storport/nf-storport-storportinitialize"><b>StorPortInitialize</b></a>. The port driver frees this memory when it removes the device. </p>

### -param r

<p>Pointer to the register. The given <i>Register</i> must be in a mapped memory space range returned by <a href="/windows-hardware/drivers/ddi/storport/nf-storport-storportgetdevicebase"><b>StorPortGetDeviceBase</b></a>. </p>

### -param v

<p>Specifies the ULONG value to be written to the HBA's register.</p>

## -see-also

<a href="/windows-hardware/drivers/ddi/srb/nf-srb-scsiportwriteregisterulong">ScsiPortWriteRegisterUlong</a>