---
UID: NF:oprghdlr.DeRegisterOpRegionHandler
title: DeRegisterOpRegionHandler function
author: windows-driver-content
description: The DeRegisterOpRegionHandler routine deregisters an operation region handler with the ACPI driver.
old-location: acpi\deregisteropregionhandler.htm
old-project: acpi
ms.assetid: b50a63cd-69eb-46a8-9d0b-660795c7047f
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: DeRegisterOpRegionHandler, DeRegisterOpRegionHandler routine [ACPI Devices], acpi.deregisteropregionhandler, opregref_e991e152-6162-4d45-9418-282afb447d18.xml, oprghdlr/DeRegisterOpRegionHandler
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: oprghdlr.h
req.include-header: Oprghdlr.h
req.target-type: Universal
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
req.lib: Oprghdlr.lib
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Oprghdlr.lib
-	Oprghdlr.dll
api_name:
-	DeRegisterOpRegionHandler
product:
- Windows
targetos: Windows
req.typenames: RILGBATOKEN, *LPRILGBATOKEN
---

# DeRegisterOpRegionHandler function


## -description


The <b>DeRegisterOpRegionHandler</b> routine deregisters an operation region handler with the <a href="https://msdn.microsoft.com/38ca54e0-defe-48b2-ab00-a5f688c2eb01">ACPI driver</a>.


## -parameters




### -param DeviceObject [in]

Pointer to the physical device object (PDO) that represents the ACPI device that defines the operation region.


### -param OperationRegionObject [in]

Specifies the operation region object returned by <a href="https://msdn.microsoft.com/library/windows/hardware/ff536158">RegisterOpRegionHandler</a> for the operation region handler.


## -returns



Returns one of the following status values.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The operating region handler was successfully registered.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
The routine could not allocate the necessary system resources.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_Xxx</b></dt>
</dl>
</td>
<td width="60%">
An internal error occurred.

</td>
</tr>
</table>
 




## -remarks



This routine is used in combination with <a href="https://msdn.microsoft.com/library/windows/hardware/ff536158">RegisterOpRegionHandler</a>. To deregister an operation region handler, the caller must specify the operation region object returned by <b>RegisterOpRegionHandler</b> when it registered the operation region handler.

For more information about operation regions, see <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/acpi/supporting-an-operation-region">Supporting an Operation Region</a>. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff536153">ACPI_OP_REGION_HANDLER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536158">RegisterOpRegionHandler</a>
 

 

