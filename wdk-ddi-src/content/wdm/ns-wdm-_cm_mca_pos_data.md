---
UID: NS:wdm._CM_MCA_POS_DATA
title: "_CM_MCA_POS_DATA"
author: windows-driver-content
description: The CM_MCA_POS_DATA structure is obsolete. It defines IBM-compatible MCA POS configuration information for a slot.
old-location: kernel\cm_mca_pos_data.htm
old-project: kernel
ms.assetid: 2b14eef2-dac4-48c8-b2a2-96bf085171aa
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: kernel.cm_mca_pos_data, *PCM_MCA_POS_DATA, CM_MCA_POS_DATA, wdm/PCM_MCA_POS_DATA, PCM_MCA_POS_DATA structure pointer [Kernel-Mode Driver Architecture], PCM_MCA_POS_DATA, _CM_MCA_POS_DATA, wdm/CM_MCA_POS_DATA, kstruct_a_a0edcef2-abf9-4660-8f40-76a2f8ff1193.xml, CM_MCA_POS_DATA structure [Kernel-Mode Driver Architecture]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
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
req.irql: PASSIVE_LEVEL (see Remarks section)
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Wdm.h
apiname:
-	CM_MCA_POS_DATA
product: Windows
targetos: Windows
req.typenames: CM_MCA_POS_DATA, *PCM_MCA_POS_DATA
req.product: Windows 10 or later.
---

# _CM_MCA_POS_DATA structure


## -description


The <b>CM_MCA_POS_DATA</b> structure is <u>obsolete</u>. It defines IBM-compatible MCA POS configuration information for a slot.


## -syntax


````
typedef struct _CM_MCA_POS_DATA {
  USHORT AdapterId;
  UCHAR  PosData1;
  UCHAR  PosData2;
  UCHAR  PosData3;
  UCHAR  PosData4;
} CM_MCA_POS_DATA, *PCM_MCA_POS_DATA;
````


## -struct-fields




### -field AdapterId



### -field PosData1



### -field PosData2



### -field PosData3



### -field PosData4



## -remarks


This structure is used by the obsolete <a href="https://msdn.microsoft.com/library/windows/hardware/ff546599">HalGetBusData</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff546606">HalGetBusDataByOffset</a> routines. 



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff546606">HalGetBusDataByOffset</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff546599">HalGetBusData</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20CM_MCA_POS_DATA structure%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

