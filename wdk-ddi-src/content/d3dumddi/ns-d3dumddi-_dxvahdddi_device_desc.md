---
UID: NS:d3dumddi._DXVAHDDDI_DEVICE_DESC
title: "_DXVAHDDDI_DEVICE_DESC"
author: windows-driver-content
description: The DXVAHDDDI_DEVICE_DESC structure describes a decode device.
old-location: display\dxvahdddi_device_desc.htm
tech.root: display
ms.assetid: c40f4151-a392-463f-888f-d575e6992062
ms.date: 5/10/2018
ms.keywords: DXVA2_Structs_ed3bcbea-9cf3-4a81-9134-e667e8121924.xml, DXVAHDDDI_DEVICE_DESC, DXVAHDDDI_DEVICE_DESC structure [Display Devices], _DXVAHDDDI_DEVICE_DESC, d3dumddi/DXVAHDDDI_DEVICE_DESC, display.dxvahdddi_device_desc
ms.topic: struct
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
req.target-min-winverclnt: DXVAHDDDI_DEVICE_DESC is supported beginning with the Windows 7 operating system.
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
-	d3dumddi.h
api_name:
-	DXVAHDDDI_DEVICE_DESC
product:
- Windows
targetos: Windows
req.typenames: DXVAHDDDI_DEVICE_DESC
---

# _DXVAHDDDI_DEVICE_DESC structure


## -description


The DXVAHDDDI_DEVICE_DESC structure describes a decode device.  


## -struct-fields




### -field pContentDesc

[in] A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff563039">DXVAHDDDI_CONTENT_DESC</a> structure that describes how the device decodes content. 


### -field Usage

[in] A <a href="https://msdn.microsoft.com/library/windows/hardware/ff563051">DXVAHDDDI_DEVICE_USAGE</a>-typed value that indicates how the decode device plays video. 


## -remarks



The driver considers the value in the <b>Usage</b> member and the information to which <b>pContentDesc</b> points to optimize its capabilities. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff563039">DXVAHDDDI_CONTENT_DESC</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563051">DXVAHDDDI_DEVICE_USAGE</a>
 

 

