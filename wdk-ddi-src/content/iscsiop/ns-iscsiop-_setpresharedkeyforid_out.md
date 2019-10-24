---
UID: NS:iscsiop._SetPresharedKeyForId_OUT
title: _SetPresharedKeyForId_OUT (iscsiop.h)
description: The SetPresharedKeyForId_OUT structure holds the output data for the SetPresharedKeyForId method.
old-location: storage\setpresharedkeyforid_out.htm
tech.root: storage
ms.assetid: 839041be-bb8c-4e02-a260-e9adcec98ff3
ms.date: 03/29/2018
ms.keywords: "*PSetPresharedKeyForId_OUT, PSetPresharedKeyForId_OUT, PSetPresharedKeyForId_OUT structure pointer [Storage Devices], SetPresharedKeyForId_OUT, SetPresharedKeyForId_OUT structure [Storage Devices], _SetPresharedKeyForId_OUT, iscsiop/PSetPresharedKeyForId_OUT, iscsiop/SetPresharedKeyForId_OUT, storage.setpresharedkeyforid_out, structs-iSCSI_c0146684-fe9e-4bca-81d2-2a09b554d006.xml"
ms.topic: struct
f1_keywords:
 - "iscsiop/SetPresharedKeyForId_OUT"
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- iscsiop.h
api_name:
- SetPresharedKeyForId_OUT
product:
- Windows
targetos: Windows
req.typenames: SetPresharedKeyForId_OUT, *PSetPresharedKeyForId_OUT
---

# _SetPresharedKeyForId_OUT structure


## -description


The SetPresharedKeyForId_OUT structure holds the output data for the <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/setpresharedkeyforid">SetPresharedKeyForId</a> method.


## -struct-fields




### -field Status

On output, the status of the <b>SetPresharedKeyForId</b> operation. For a list of status qualifiers, see <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/iscsi-status-qualifiers">ISCSI_STATUS_QUALIFIERS</a>. 


## -remarks



You must implement this method.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/storage/iscsi-status-qualifiers">ISCSI_STATUS_QUALIFIERS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/storage/setpresharedkeyforid">SetPresharedKeyForId</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/iscsiop/ns-iscsiop-_setpresharedkeyforid_in">SetPresharedKeyForId_IN</a>
 

 

