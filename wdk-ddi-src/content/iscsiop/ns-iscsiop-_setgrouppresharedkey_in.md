---
UID: NS:iscsiop._SetGroupPresharedKey_IN
title: "_SetGroupPresharedKey_IN"
author: windows-driver-content
description: The SetGroupPresharedKey_IN structure holds the input data for the SetGroupPresharedKey method.
old-location: storage\setgrouppresharedkey_in.htm
old-project: storage
ms.assetid: fe5e1f75-ebd0-4856-bb77-14efb52fbce0
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PSetGroupPresharedKey_IN, PSetGroupPresharedKey_IN, PSetGroupPresharedKey_IN structure pointer [Storage Devices], SetGroupPresharedKey_IN, SetGroupPresharedKey_IN structure [Storage Devices], _SetGroupPresharedKey_IN, iscsiop/PSetGroupPresharedKey_IN, iscsiop/SetGroupPresharedKey_IN, storage.setgrouppresharedkey_in, structs-iSCSI_0109dfff-f30e-4f15-ab25-4a290b2fc2f4.xml"
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
-	SetGroupPresharedKey_IN
product: Windows
targetos: Windows
req.typenames: SetGroupPresharedKey_IN, *PSetGroupPresharedKey_IN
---

# _SetGroupPresharedKey_IN structure


## -description


The SetGroupPresharedKey_IN structure holds the input data for the <a href="https://msdn.microsoft.com/library/windows/hardware/ff565693">SetGroupPresharedKey</a> method.


## -struct-fields




### -field KeySize

The size, in bytes, of the key in <b>Key</b><i>.</i>


### -field Key

The preshared group key<i>.</i>


## -remarks



You must implement this method.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff565693">SetGroupPresharedKey</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff565697">SetGroupPresharedKey_OUT</a>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20SetGroupPresharedKey_IN structure%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

