---
UID: NS:d3dkmdt._DXGKMDT_OPM_HDCP_KEY_SELECTION_VECTOR
title: "_DXGKMDT_OPM_HDCP_KEY_SELECTION_VECTOR" (d3dkmdt.h)
description: The DXGKMDT_OPM_HDCP_KEY_SELECTION_VECTOR structure contains a key-selection vector (KSV) for a High-bandwidth Digital Content Protection (HDCP) protected output.
old-location: display\dxgkmdt_opm_hdcp_key_selection_vector.htm
tech.root: display
ms.assetid: a69eae04-a7e0-4d0c-a3e0-d49905096c8e
ms.date: 05/10/2018
ms.keywords: DXGKMDT_OPM_HDCP_KEY_SELECTION_VECTOR, DXGKMDT_OPM_HDCP_KEY_SELECTION_VECTOR structure [Display Devices], DmStructs_381ec3d0-fcf3-4153-8cc3-f2dda3f9684f.xml, _DXGKMDT_OPM_HDCP_KEY_SELECTION_VECTOR, d3dkmdt/DXGKMDT_OPM_HDCP_KEY_SELECTION_VECTOR, display.dxgkmdt_opm_hdcp_key_selection_vector
ms.topic: struct
req.header: d3dkmdt.h
req.include-header: D3dkmdt.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
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
-	d3dkmdt.h
api_name:
-	DXGKMDT_OPM_HDCP_KEY_SELECTION_VECTOR
product:
- Windows
targetos: Windows
req.typenames: DXGKMDT_OPM_HDCP_KEY_SELECTION_VECTOR
---

# _DXGKMDT_OPM_HDCP_KEY_SELECTION_VECTOR structure


## -description


The DXGKMDT_OPM_HDCP_KEY_SELECTION_VECTOR structure contains a key-selection vector (KSV) for a High-bandwidth Digital Content Protection (HDCP) protected output.


## -struct-fields




### -field abKeySelectionVector

A 5-byte array that comprises the HDCP KSV. Byte 0 is the least significant byte and byte 4 is the most significant byte. 


## -remarks



For more information about the HDCP KSV, see the <a href="https://go.microsoft.com/fwlink/p/?linkid=38728">HDCP Specification Revision 1.1</a>. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff560854">DXGKMDT_OPM_CONNECTED_HDCP_DEVICE_INFORMATION</a>
 

 

