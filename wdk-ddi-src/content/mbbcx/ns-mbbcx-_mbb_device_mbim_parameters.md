---
UID: NS:mbbcx._MBB_DEVICE_MBIM_PARAMETERS
title: _MBB_DEVICE_MBIM_PARAMETERS (mbbcx.h)
description: The client driver uses the MBB_DEVICE_MBIM_PARAMETERS structure to describe its MBIM specification-related parameters to the MBBCx framework.
tech.root: netvista
ms.assetid: 814daf06-b7f3-4cee-8b74-8b0a13a6292a
ms.date: 02/06/2019
ms.topic: struct
f1_keywords:
 - "mbbcx/-	_MBB_DEVICE_MBIM_PARAMETERS"
ms.keywords: _MBB_DEVICE_MBIM_PARAMETERS, MBB_DEVICE_MBIM_PARAMETERS, *PMBB_DEVICE_MBIM_PARAMETERS, 
req.header: mbbcx.h
req.include-header:
req.target-type:
req.target-min-winverclnt: Windows 10, version 1903
req.target-min-winversvr:
req.kmdf-ver: 1.29
req.umdf-ver:
req.lib:
req.dll:
req.ddi-compliance:
req.unicode-ansi:
req.max-support:
req.typenames: MBB_DEVICE_MBIM_PARAMETERS, *PMBB_DEVICE_MBIM_PARAMETERS
topic_type: 
- apiref
api_type: 
- HeaderDef
api_location: 
- mbbcx.h
api_name: 
- _MBB_DEVICE_MBIM_PARAMETERS
product:
- Windows
targetos: Windows
ms.custom: RS5
---

# _MBB_DEVICE_MBIM_PARAMETERS structure

## -description

> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
> 
> MBBCx is preview only in Windows 10, version 1903.

The client driver uses the **MBB_DEVICE_MBIM_PARAMETERS** structure to describe its MBIM specification-related parameters to the MBBCx framework.

## -struct-fields

### -field Size

The size of this structure, in bytes.
 
### -field Version

An [**MBB_MBIM_VERSION**](ne-mbbcx-_mbb_mbim_version.md) value that defines the version of the MBIM specification that the client driver supports. The value of this field must be **MBB_MBIM_VERSION1_0_ERRATA**.

> [!IMPORTANT]
> The client driver and device must support the MBIM specification Rev 1.0 Errata-1.

### -field ExtendedVersion

An [**MBB_MBIM_EXTENDED_VERSION**](../mbbcx/ne-mbbcx-_mbb_mbim_extended_version.md) value that defines the version of the extended MBIM specification that the client driver supports. The value of this field must be **MBB_MBIM_EXTENDED_VERSION2_0**.
 
### -field MaximumFragmentSize

The maximum size of MBIM control messages that the client driver can support.

The MBBCx framework uses the value of this field to determine if it needs to fragment the MBIM message when it later calls into the client driver's [*EvtMbbDeviceSendMbimFragment*](nc-mbbcx-evt_mbb_device_send_mbim_fragment.md) callback function to issue commands.

## -remarks

Call [**MBB_DEVICE_MBIM_PARAMETERS_INIT**](nf-mbbcx-mbb_device_mbim_parameters_init.md) to intialize this structure.

## -see-also
