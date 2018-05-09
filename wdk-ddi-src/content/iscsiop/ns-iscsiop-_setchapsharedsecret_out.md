---
UID: NS:iscsiop._SetCHAPSharedSecret_OUT
title: "_SetCHAPSharedSecret_OUT"
author: windows-driver-content
description: The SetCHAPSharedSecret_OUT structure holds the output data for the SetCHAPSharedSecret method.
old-location: storage\setchapsharedsecret_out.htm
old-project: storage
ms.assetid: a169a5b2-5303-41fc-80d2-69b44fd45c47
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: "*PSetCHAPSharedSecret_OUT, PSetCHAPSharedSecret_OUT, PSetCHAPSharedSecret_OUT structure pointer [Storage Devices], SetCHAPSharedSecret_OUT, SetCHAPSharedSecret_OUT structure [Storage Devices], _SetCHAPSharedSecret_OUT, iscsiop/PSetCHAPSharedSecret_OUT, iscsiop/SetCHAPSharedSecret_OUT, storage.setchapsharedsecret_out, structs-iSCSI_f11f03d2-424a-4537-9cbd-f4fd3ca0e59d.xml"
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
-	SetCHAPSharedSecret_OUT
product:
- Windows
targetos: Windows
req.typenames: SetCHAPSharedSecret_OUT, *PSetCHAPSharedSecret_OUT
---

# _SetCHAPSharedSecret_OUT structure


## -description


The SetCHAPSharedSecret_OUT structure holds the output data for the <a href="https://msdn.microsoft.com/library/windows/hardware/ff565585">SetCHAPSharedSecret</a> method.


## -struct-fields




### -field Status

On output, the status of the <b>SetCHAPSharedSecret</b> operation. For a list of status qualifiers, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff561568">ISCSI_STATUS_QUALIFIERS</a>.  


## -remarks



You must implement this method.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff561568">ISCSI_STATUS_QUALIFIERS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff565585">SetCHAPSharedSecret</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff565595">SetCHAPSharedSecret_IN</a>
 

 

