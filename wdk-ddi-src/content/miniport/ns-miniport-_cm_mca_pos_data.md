---
UID: NS:miniport._CM_MCA_POS_DATA
title: _CM_MCA_POS_DATA (miniport.h)
description: The _CM_MCA_POS_DATA structure (miniport.h) is obsolete. It defines IBM-compatible MCA POS configuration information for a slot.
old-location: kernel\cm_mca_pos_data.htm
tech.root: kernel
ms.date: 04/30/2018
keywords: ["CM_MCA_POS_DATA structure"]
ms.keywords: "*PCM_MCA_POS_DATA, CM_MCA_POS_DATA, CM_MCA_POS_DATA structure [Kernel-Mode Driver Architecture], PCM_MCA_POS_DATA, PCM_MCA_POS_DATA structure pointer [Kernel-Mode Driver Architecture], _CM_MCA_POS_DATA, kernel.cm_mca_pos_data, kstruct_a_a0edcef2-abf9-4660-8f40-76a2f8ff1193.xml, wdm/CM_MCA_POS_DATA, wdm/PCM_MCA_POS_DATA"
req.header: miniport.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h, Miniport.h
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
req.typenames: CM_MCA_POS_DATA, *PCM_MCA_POS_DATA
f1_keywords:
 - _CM_MCA_POS_DATA
 - miniport/_CM_MCA_POS_DATA
 - PCM_MCA_POS_DATA
 - miniport/PCM_MCA_POS_DATA
 - CM_MCA_POS_DATA
 - miniport/CM_MCA_POS_DATA
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Wdm.h
api_name:
 - _CM_MCA_POS_DATA
 - PCM_MCA_POS_DATA
 - CM_MCA_POS_DATA
---

# _CM_MCA_POS_DATA structure (miniport.h)


## -description

The <b>CM_MCA_POS_DATA</b> structure is <u>obsolete</u>. It defines IBM-compatible MCA POS configuration information for a slot.

## -struct-fields

### -field AdapterId

### -field PosData1

### -field PosData2

### -field PosData3

### -field PosData4

## -remarks

This structure is used by the obsolete <a href="/previous-versions/windows/hardware/drivers/ff546644(v=vs.85)">HalGetBusData</a> and <a href="/previous-versions/windows/hardware/drivers/ff546644(v=vs.85)">HalGetBusDataByOffset</a> routines.

## -see-also

<a href="/previous-versions/windows/hardware/drivers/ff546644(v=vs.85)">HalGetBusData</a>



<a href="/previous-versions/windows/hardware/drivers/ff546644(v=vs.85)">HalGetBusDataByOffset</a>

