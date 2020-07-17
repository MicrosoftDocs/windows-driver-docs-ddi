---
UID: NE:scsiwmi.__unnamed_enum_0
title: SCSIWMI_ENABLE_DISABLE_CONTROL (scsiwmi.h)
description: The SCSIWMI_ENABLE_DISABLE_CONTROL enumerator is used to specify what to enable or disable.
old-location: storage\scsiwmi_enable_disable_control.htm
tech.root: storage
ms.assetid: 0327bdc0-e4a4-4c2f-a9b9-5854e3330068
ms.date: 03/29/2018
keywords: ["SCSIWMI_ENABLE_DISABLE_CONTROL enumeration"]
ms.keywords: SCSIWMI_ENABLE_DISABLE_CONTROL, SCSIWMI_ENABLE_DISABLE_CONTROL enumeration [Storage Devices], ScsiWmiDataBlockControl, ScsiWmiEventControl, scsiwmi/SCSIWMI_ENABLE_DISABLE_CONTROL, scsiwmi/ScsiWmiDataBlockControl, scsiwmi/ScsiWmiEventControl, storage.scsiwmi_enable_disable_control, structs-scsibus_58a70c92-6ee7-4385-b212-45672a12ac8b.xml
f1_keywords:
 - "scsiwmi/SCSIWMI_ENABLE_DISABLE_CONTROL"
 - "SCSIWMI_ENABLE_DISABLE_CONTROL"
req.header: scsiwmi.h
req.include-header: Scsiwmi.h
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- scsiwmi.h
api_name:
- SCSIWMI_ENABLE_DISABLE_CONTROL
product:
- Windows
targetos: Windows
req.typenames: SCSIWMI_ENABLE_DISABLE_CONTROL
---

# SCSIWMI_ENABLE_DISABLE_CONTROL enumeration


## -description


The SCSIWMI_ENABLE_DISABLE_CONTROL enumerator is used to specify what to enable or disable. 
<div class="alert"><b>Note</b>  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## -enum-fields




### -field ScsiWmiEventControl

Indicates that a WMI event is to be enabled or disabled. 


### -field ScsiWmiDataBlockControl

Indicates that a data collection for a block is to be enabled or disabled.  


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wmilib/nc-wmilib-wmi_function_control_callback">DpWmiFunctionControl</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/scsiwmi/nc-scsiwmi-pscsiwmi_function_control">HwScsiWmiFunctionControl</a>
 

 

