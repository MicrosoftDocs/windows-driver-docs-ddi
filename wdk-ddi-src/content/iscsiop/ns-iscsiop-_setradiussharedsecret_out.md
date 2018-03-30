---
UID: NS:iscsiop._SetRADIUSSharedSecret_OUT
title: "_SetRADIUSSharedSecret_OUT"
author: windows-driver-content
description: The SetRADIUSSharedSecret_OUT structure holds the output data for the SetRADIUSSharedSecret method.
old-location: storage\setradiussharedsecret_out.htm
old-project: storage
ms.assetid: 55be7611-3249-4109-a142-c0115dfebb98
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PSetRADIUSSharedSecret_OUT, PSetRADIUSSharedSecret_OUT, PSetRADIUSSharedSecret_OUT structure pointer [Storage Devices], SetRADIUSSharedSecret_OUT, SetRADIUSSharedSecret_OUT structure [Storage Devices], _SetRADIUSSharedSecret_OUT, iscsiop/PSetRADIUSSharedSecret_OUT, iscsiop/SetRADIUSSharedSecret_OUT, storage.setradiussharedsecret_out, structs-iSCSI_497fc66e-8a5d-4390-9229-622b359776bc.xml"
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
-	SetRADIUSSharedSecret_OUT
product: Windows
targetos: Windows
req.typenames: SetRADIUSSharedSecret_OUT, *PSetRADIUSSharedSecret_OUT
---

# _SetRADIUSSharedSecret_OUT structure


## -description


The SetRADIUSSharedSecret_OUT structure holds the output data for the <a href="https://msdn.microsoft.com/library/windows/hardware/ff565815">SetRADIUSSharedSecret</a> method.


## -struct-fields




### -field Status

On output, the status of the <b>SetRADIUSSharedSecret</b> operation. For a list of status qualifiers, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff561568">ISCSI_STATUS_QUALIFIERS</a>.


## -remarks



You must implement this method.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff561568">ISCSI_STATUS_QUALIFIERS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff565815">SetRADIUSSharedSecret</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff565831">SetRADIUSSharedSecret_IN</a>
 

 

