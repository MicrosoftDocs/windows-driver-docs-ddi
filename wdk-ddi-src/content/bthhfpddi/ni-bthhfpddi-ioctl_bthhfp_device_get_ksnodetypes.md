---
UID: NI:bthhfpddi.IOCTL_BTHHFP_DEVICE_GET_KSNODETYPES
title: IOCTL_BTHHFP_DEVICE_GET_KSNODETYPES (bthhfpddi.h)
description: The IOCTL_BTHHFP_DEVICE_GET_KSNODETYPES IOCTL Gets the KSNODE types that best describe the Bluetooth device’s input and output.
old-location: audio\ioctl_bthhfp_device_get_ksnodetypes.htm
tech.root: audio
ms.assetid: 6862B0FD-9A7B-40BF-8123-673EE443DE84
ms.date: 05/08/2018
keywords: ["IOCTL_BTHHFP_DEVICE_GET_KSNODETYPES IOCTL"]
ms.keywords: IOCTL_BTHHFP_DEVICE_GET_KSNODETYPES, IOCTL_BTHHFP_DEVICE_GET_KSNODETYPES control, IOCTL_BTHHFP_DEVICE_GET_KSNODETYPES control code [Audio Devices], audio.ioctl_bthhfp_device_get_ksnodetypes, bthhfpddi/IOCTL_BTHHFP_DEVICE_GET_KSNODETYPES
req.header: bthhfpddi.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
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
req.typenames: 
f1_keywords:
 - IOCTL_BTHHFP_DEVICE_GET_KSNODETYPES
 - bthhfpddi/IOCTL_BTHHFP_DEVICE_GET_KSNODETYPES
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Bthhfpddi.h
api_name:
 - IOCTL_BTHHFP_DEVICE_GET_KSNODETYPES
---

# IOCTL_BTHHFP_DEVICE_GET_KSNODETYPES IOCTL


## -description

The <b>IOCTL_BTHHFP_DEVICE_GET_KSNODETYPES</b> 
   IOCTL Gets the KSNODE types that best describe the Bluetooth device’s input and output.
<div class="alert"><b>Note</b>  This IOCTL has been deprecated for Windows 8.1, so you should use <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthhfpddi/ni-bthhfpddi-ioctl_bthhfp_device_get_descriptor">IOCTL_BTHHFP_DEVICE_GET_DESCRIPTOR</a> instead.</div><div> </div>

## -ioctlparameters

### -input-buffer

None.

### -input-buffer-length

None.

### -output-buffer

<div class="code"><span codelanguage="ManagedCPlusPlus"><table>
<tr>
<th>C++</th>
</tr>
<tr>
<td>
<pre>struct
{
    GUID OutputType;
    GUID InputType;
}

```


### -output-buffer-length

The size of the specified structure.

### -in-out-buffer

### -inout-buffer-length

### -status-block

N/A

## -InputType

 The KSNODE type for the intput.

## -OutputType

 The KSNODE type for the output.

## -remarks

This request completes immediately.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/audio/bluetooth-hfp-ddi-ioctls">Bluetooth HFP DDI IOCTLs</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthhfpddi/ni-bthhfpddi-ioctl_bthhfp_device_get_descriptor">IOCTL_BTHHFP_DEVICE_GET_DESCRIPTOR</a>

