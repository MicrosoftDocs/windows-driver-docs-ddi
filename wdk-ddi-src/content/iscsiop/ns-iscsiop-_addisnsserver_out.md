---
UID: NS:iscsiop._AddiSNSServer_OUT
title: _AddiSNSServer_OUT (iscsiop.h)
description: The AddiSNSServer_OUT structure holds the output data for the user-mode AddISNSServer method.
old-location: storage\addisnsserver_out.htm
tech.root: storage
ms.assetid: f1c02d19-9e96-4fd6-b950-ae02b6f3bba4
ms.date: 03/29/2018
ms.keywords: "*PAddiSNSServer_OUT, AddiSNSServer_OUT, AddiSNSServer_OUT structure [Storage Devices], PAddiSNSServer_OUT, PAddiSNSServer_OUT structure pointer [Storage Devices], _AddiSNSServer_OUT, iscsiop/AddiSNSServer_OUT, iscsiop/PAddiSNSServer_OUT, storage.addisnsserver_out, structs-iSCSI_d1d3f4d6-6c48-4f6d-bc5e-9449a4b87d2b.xml"
ms.topic: struct
f1_keywords:
 - "iscsiop/AddiSNSServer_OUT"
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
- AddiSNSServer_OUT
product:
- Windows
targetos: Windows
req.typenames: AddiSNSServer_OUT, *PAddiSNSServer_OUT
---

# _AddiSNSServer_OUT structure


## -description


The AddiSNSServer_OUT structure holds the output data for the user-mode <b>AddISNSServer</b> method.


## -struct-fields




### -field Status

On output from <b>AddISNSServer</b>, the status of the <b>AddISNSServer</b> operation. For a list of status qualifiers, see <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/iscsi-status-qualifiers">ISCSI_STATUS_QUALIFIERS</a>.  


## -remarks



It is optional that you implement this method.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/iscsiop/ns-iscsiop-_addisnsserver_in">AddiSNSServer_IN</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/storage/iscsi-status-qualifiers">ISCSI_STATUS_QUALIFIERS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/storage/msiscsi-operations-wmi-class">MSiSCSI_Operations WMI Class</a>
 

 

