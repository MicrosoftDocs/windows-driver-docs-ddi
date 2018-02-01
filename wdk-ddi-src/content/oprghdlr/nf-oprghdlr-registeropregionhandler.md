---
UID: NF:oprghdlr.RegisterOpRegionHandler
title: RegisterOpRegionHandler function
author: windows-driver-content
description: The RegisterOpRegionHandler routine registers an operation region handler with the ACPI driver.
old-location: acpi\registeropregionhandler.htm
old-project: acpi
ms.assetid: 5795a1d1-0e13-4f9f-b2f2-37bbd71bde7a
ms.author: windowsdriverdev
ms.date: 12/31/2017
ms.keywords: RegisterOpRegionHandler, RegisterOpRegionHandler routine [ACPI Devices], acpi.registeropregionhandler, opregref_9742e50b-613d-4191-b0a2-6d1b0f365494.xml, oprghdlr/RegisterOpRegionHandler
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Oprghdlr.lib
-	Oprghdlr.dll
apiname:
-	RegisterOpRegionHandler
product: Windows
targetos: Windows
req.typenames: RILGBATOKEN, *LPRILGBATOKEN
---

# RegisterOpRegionHandler function


## -description


The <b>RegisterOpRegionHandler</b> routine registers an operation region handler with the <a href="https://msdn.microsoft.com/38ca54e0-defe-48b2-ab00-a5f688c2eb01">ACPI driver</a>.


## -syntax


````
NTSTATUS RegisterOpRegionHandler(
  _In_  PDEVICE_OBJECT          DeviceObject,
  _In_  ULONG                   AccessType,
  _In_  ULONG                   RegionSpace,
  _In_  PACPI_OP_REGION_HANDLER Handler,
  _In_  PVOID                   Context,
  _In_  ULONG                   Flags,
  _Out_ PVOID                   *OperationRegionObject
);
````


## -parameters




### -param DeviceObject [in]

Pointer to the physical device object (<a href="https://msdn.microsoft.com/139a10e9-203b-499b-9291-8537eae9189c">PDO</a>) that represents the ACPI device that defines the operation region.


### -param AccessType [in]

Specifies ACPI_OPREGION_ACCESS_AS_COOKED.


### -param RegionSpace [in]

Specifies one of the following types of region space.
<table>
<tr>
<th>Region Space Identifier</th>
<th>Description</th>
</tr>
<tr>
<td>
ACPI_OPREGION_REGION_SPACE_MEMORY

</td>
<td>
System memory

</td>
</tr>
<tr>
<td>
ACPI_OPREGION_REGION_SPACE_IO

</td>
<td>
I/O space

</td>
</tr>
<tr>
<td>
ACPI_OPREGION_REGION_SPACE_PCI_CONFIG

</td>
<td>
PCI configuration

</td>
</tr>
<tr>
<td>
ACPI_OPREGION_REGION_SPACE_EC

</td>
<td>
Embedded controller

</td>
</tr>
<tr>
<td>
ACPI_OPREGION_REGION_SPACE_SMB

</td>
<td>
System Management Bus

</td>
</tr>
<tr>
<td>
ACPI_OPREGION_REGION_SPACE_CMOS_CONFIG

</td>
<td>
CMOS configuration

</td>
</tr>
<tr>
<td>
ACPI_OPREGION_REGION_SPACE_PCIBARTARGET

</td>
<td>
PCI Base Address Register

</td>
</tr>
<tr>
<td>
Vendor-defined value from 0x80 to 0xFF

</td>
<td>
Vendor-defined

</td>
</tr>
</table> 


### -param Handler [in]

Pointer to the <a href="..\oprghdlr\nc-oprghdlr-acpi_op_region_handler.md">ACPI_OP_REGION_HANDLER</a>-typed operation region handler (supplied by an ACPI device function driver).


### -param Context [in]

Pointer to a device-specific operation region context (supplied by an ACPI device function driver).


### -param Flags [in]

Reserved for internal use.


### -param OperationRegionObject [out]

Pointer to caller-allocated buffer that, on output, contains a pointer to the operation region object that the ACPI driver creates for the operation region.


## -returns


Returns one of the following status values:
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
<dt><b>STATUS_ACPI_INVALID_DATA</b></dt>
</dl>
</td>
<td width="60%">
The specified information is not valid.

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


The operation region context specified by <i>Context</i> is device-specific and is only used by the function driver. Typically, the context is the device extension for the functional device object (<a href="https://msdn.microsoft.com/f697e0db-1db0-4a81-94d8-0ca079885480">FDO</a>). The ACPI driver passes this context back to the function driver when it calls the operation region handler. The operation region object is only used by a function driver to uniquely identify the operation region when it deregisters the operation region handler.

For more information about operation regions, see <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/acpi/supporting-an-operation-region">Supporting an Operation Region</a>. 



## -see-also

<a href="..\oprghdlr\nc-oprghdlr-acpi_op_region_handler.md">ACPI_OP_REGION_HANDLER</a>

<a href="..\oprghdlr\nf-oprghdlr-deregisteropregionhandler.md">DeRegisterOpRegionHandler</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [acpi\acpi]:%20RegisterOpRegionHandler routine%20 RELEASE:%20(12/31/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

