---
UID: NS:iscsiop._SetGenerationalGuid_OUT
title: "_SetGenerationalGuid_OUT"
author: windows-driver-content
description: The SetGenerationalGuid_OUT structure holds the output data for the SetGenerationalGuid method.
old-location: storage\setgenerationalguid_out.htm
old-project: storage
ms.assetid: 7b697241-6411-4fb0-b633-502233f2d155
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PSetGenerationalGuid_OUT, PSetGenerationalGuid_OUT, PSetGenerationalGuid_OUT structure pointer [Storage Devices], SetGenerationalGuid_OUT, SetGenerationalGuid_OUT structure [Storage Devices], _SetGenerationalGuid_OUT, iscsiop/PSetGenerationalGuid_OUT, iscsiop/SetGenerationalGuid_OUT, storage.setgenerationalguid_out, structs-iSCSI_80d71c4a-f542-4b19-9bbe-b1e8e7cc21cd.xml"
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
-	SetGenerationalGuid_OUT
product: Windows
targetos: Windows
req.typenames: SetGenerationalGuid_OUT, *PSetGenerationalGuid_OUT
---

# _SetGenerationalGuid_OUT structure


## -description


The SetGenerationalGuid_OUT structure holds the output data for the <a href="https://msdn.microsoft.com/library/windows/hardware/ff565678">SetGenerationalGuid</a> method.


## -struct-fields




### -field Status

On output, the status of the <b>SetGenerationalGuid</b> operation. For a list of status qualifiers, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff561568">ISCSI_STATUS_QUALIFIERS</a>. 


## -remarks



You must implement this method.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff561568">ISCSI_STATUS_QUALIFIERS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff565678">SetGenerationalGuid</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff565681">SetGenerationalGuid_IN</a>
 

 

