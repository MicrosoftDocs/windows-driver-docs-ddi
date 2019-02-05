---
UID: NS:d3dkmdt._DXGK_FAULT_ERROR_CODE
title: _DXGK_FAULT_ERROR_CODE (d3dkmdt.h)
description: The DXGK_FAULT_ERROR_CODE structure provides a status code for the graphics processing unit (GPU) error reported via a page fault interrupt.
old-location: display\dxgk_fault_error_code.htm
tech.root: display
ms.assetid: 753FC177-D430-40E5-98CD-B3BDFD47ACEF
ms.date: 05/10/2018
ms.keywords: DXGK_FAULT_ERROR_CODE, DXGK_FAULT_ERROR_CODE structure [Display Devices], _DXGK_FAULT_ERROR_CODE, d3dkmdt/DXGK_FAULT_ERROR_CODE, display.dxgk_fault_error_code
ms.topic: struct
req.header: d3dkmdt.h
req.include-header: D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
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
-	D3dkmdt.h
api_name:
-	DXGK_FAULT_ERROR_CODE
product:
- Windows
targetos: Windows
req.typenames: DXGK_FAULT_ERROR_CODE
---

# _DXGK_FAULT_ERROR_CODE structure


## -description


The <b>DXGK_FAULT_ERROR_CODE</b> structure provides a status code for the graphics processing unit (GPU) error reported via a page fault interrupt.


## -struct-fields




### -field IsDeviceSpecificCode

When set, this indicates that the GPU error code is specific to the particular vendor. In this case, <b>DeviceSpecificCode</b> should be set to a vendor specific error code.

When not set, this indicates that the GPU error can be described via a set of predefined values in <a href="https://msdn.microsoft.com/library/windows/hardware/dn906347">DXGK_GENERAL_ERROR_CODE</a> enumeration. <b>GeneralErrorCode</b> value should be set to the corresponding error code.


### -field GeneralErrorCode

General error code defined by <a href="https://msdn.microsoft.com/library/windows/hardware/dn906347">DXGK_GENERAL_ERROR_CODE</a>.


### -field IsDeviceSpecificCodeReservedBit

Same as <b>IsDeviceSpecificCode</b> member above:

When set, this indicates that the GPU error code is specific to the particular vendor. In this case, <b>DeviceSpecificCode</b> should be set to a vendor specific error code.

When not set, this indicates that the GPU error can be described via a set of predefined values in <a href="https://msdn.microsoft.com/library/windows/hardware/dn906347">DXGK_GENERAL_ERROR_CODE</a> enumeration. <b>GeneralErrorCode</b> value should be set to the corresponding error code.


### -field DeviceSpecificCode

A device specific error code.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/dn906347">DXGK_GENERAL_ERROR_CODE</a>
 

 

