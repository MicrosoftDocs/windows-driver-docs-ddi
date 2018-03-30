---
UID: NS:iscsiop._SetGroupPresharedKey_OUT
title: "_SetGroupPresharedKey_OUT"
author: windows-driver-content
description: The SetGroupPresharedKey_OUT structure holds the output data for the SetGroupPresharedKey method.
old-location: storage\setgrouppresharedkey_out.htm
old-project: storage
ms.assetid: 4ea5e428-783c-4a28-bec5-42106425ee1f
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PSetGroupPresharedKey_OUT, PSetGroupPresharedKey_OUT, PSetGroupPresharedKey_OUT structure pointer [Storage Devices], SetGroupPresharedKey_OUT, SetGroupPresharedKey_OUT structure [Storage Devices], _SetGroupPresharedKey_OUT, iscsiop/PSetGroupPresharedKey_OUT, iscsiop/SetGroupPresharedKey_OUT, storage.setgrouppresharedkey_out, structs-iSCSI_81186f6a-bf08-42eb-a3d8-ae195cdd8135.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: iscsiop.h
req.include-header: Iscsiop.h
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	iscsiop.h
api_name:
-	SetGroupPresharedKey_OUT
product: Windows
targetos: Windows
req.typenames: SetGroupPresharedKey_OUT, *PSetGroupPresharedKey_OUT
---

# _SetGroupPresharedKey_OUT structure


## -description


The SetGroupPresharedKey_OUT structure holds the output data for the <a href="https://msdn.microsoft.com/library/windows/hardware/ff565693">SetGroupPresharedKey</a> method.


## -struct-fields




### -field Status

On output, the status of the <b>SetGroupPresharedKey</b> operation. For a list of status qualifiers, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff561568">ISCSI_STATUS_QUALIFIERS</a>. 


## -remarks



You must implement this method.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff561568">ISCSI_STATUS_QUALIFIERS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff565693">SetGroupPresharedKey</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff565695">SetGroupPresharedKey_IN</a>
 

 

