---
UID: NF:oprghdlr.DeRegisterOpRegionHandler
title: DeRegisterOpRegionHandler function
author: windows-driver-content
description: The DeRegisterOpRegionHandler routine deregisters an operation region handler with the ACPI driver.
old-location: acpi\deregisteropregionhandler.htm
old-project: acpi
ms.assetid: b50a63cd-69eb-46a8-9d0b-660795c7047f
ms.author: windowsdriverdev
ms.date: 12/31/2017
ms.keywords: DeRegisterOpRegionHandler
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
req.alt-api: DeRegisterOpRegionHandler
req.alt-loc: Oprghdlr.lib,Oprghdlr.dll
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
req.typenames: *LPRILGBATOKEN, RILGBATOKEN
---

# DeRegisterOpRegionHandler function



## -description
The <b>DeRegisterOpRegionHandler</b> routine deregisters an operation region handler with the <a href="https://msdn.microsoft.com/38ca54e0-defe-48b2-ab00-a5f688c2eb01">ACPI driver</a>.



## -syntax

````
NTSTATUS DeRegisterOpRegionHandler(
  _In_ PDEVICE_OBJECT DeviceObject,
  _In_ PVOID          OperationRegionObject
);
````


## -parameters

### -param DeviceObject [in]

Pointer to the physical device object (PDO) that represents the ACPI device that defines the operation region.


### -param OperationRegionObject [in]

Specifies the operation region object returned by <a href="..\oprghdlr\nf-oprghdlr-registeropregionhandler.md">RegisterOpRegionHandler</a> for the operation region handler.


## -returns
Returns one of the following status values.
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>The operating region handler was successfully registered.
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>The routine could not allocate the necessary system resources.
<dl>
<dt><b>STATUS_Xxx</b></dt>
</dl>An internal error occurred.

 


## -remarks
This routine is used in combination with <a href="..\oprghdlr\nf-oprghdlr-registeropregionhandler.md">RegisterOpRegionHandler</a>. To deregister an operation region handler, the caller must specify the operation region object returned by <b>RegisterOpRegionHandler</b> when it registered the operation region handler.

For more information about operation regions, see <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/acpi/supporting-an-operation-region">Supporting an Operation Region</a>. 


## -see-also
<dl>
<dt>
<a href="..\oprghdlr\nf-oprghdlr-registeropregionhandler.md">RegisterOpRegionHandler</a>
</dt>
<dt>
<a href="..\oprghdlr\nc-oprghdlr-acpi_op_region_handler.md">ACPI_OP_REGION_HANDLER</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [acpi\acpi]:%20DeRegisterOpRegionHandler routine%20 RELEASE:%20(12/31/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

