---
UID: NF:winddiui.DrvUpgradePrinter
title: DrvUpgradePrinter function
author: windows-driver-content
description: A printer interface DLL's DrvUpgradePrinter function is used for updating a printer's registry settings when a new version of the driver is added to a system.
old-location: print\drvupgradeprinter.htm
tech.root: print
ms.assetid: 5a8a764d-48bf-48f9-831a-ac22767aeca6
ms.date: 4/20/2018
ms.keywords: DrvUpgradePrinter, DrvUpgradePrinter function [Print Devices], print.drvupgradeprinter, print_interface-graphics_ab060948-18bc-4b0f-a504-320083fcb173.xml, winddiui/DrvUpgradePrinter
ms.topic: function
req.header: winddiui.h
req.include-header: Winddiui.h
req.target-type: Desktop
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
-	winddiui.h
api_name:
-	DrvUpgradePrinter
product:
- Windows
targetos: Windows
req.typenames: 
---

# DrvUpgradePrinter function


## -description


A printer interface DLL's <b>DrvUpgradePrinter</b> function is used for updating a printer's registry settings when a new version of the driver is added to a system.


## -parameters




### -param Level

Caller-supplied value indicating the type of structure pointed to by <i>pDriverUpgradeInfo</i>, as indicated in the following table.

<table>
<tr>
<th><i>Level</i> Value</th>
<th>Structure pointed to by <i>pDriverUpgradeInfo</i></th>
</tr>
<tr>
<td>
1

</td>
<td>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff548522">DRIVER_UPGRADE_INFO_1</a>


</td>
</tr>
<tr>
<td>
2

</td>
<td>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff548527">DRIVER_UPGRADE_INFO_2</a>


</td>
</tr>
</table>
 


### -param pDriverUpgradeInfo [in, optional]

Caller-supplied pointer to a structure whose type is identified by <i>dwLevel</i>. 


## -returns



If the operation succeeds, the function should return <b>TRUE</b>; otherwise, it should call SetLastError to set an error code and return <b>FALSE</b>.




## -remarks



A <a href="https://msdn.microsoft.com/2a8cf38f-8e27-4e08-9c0f-5d1a4cd854ac">printer interface DLL</a> can optionally provide a <b>DrvUpgradePrinter</b> function. If it does, the spooler calls it for every printer when the printer driver is copied onto the system. This occurs when a system is upgraded from one operating system release to the next, or when an application updates a printer driver by calling the Win32 <b>AddPrinterDriver</b> function.

Often, a new driver version requires registry settings that are different from those of the old version. The <b>DrvUpgradePrinter</b> function's purpose is to update the registry so it is compatible with the driver. For more information about storing printer information in the registry, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff548564">DrvPrinterEvent</a>.

For Windows 2000 and later, when the spooler calls <b>DrvUpgradePrinter</b>, it supplies a DRIVER_UPGRADE_INFO_2 structure pointer for <i>pDriverUpgradeInfo</i>. If the function returns <b>FALSE</b>, the spooler calls the function again, this time specifying a DRIVER_UPGRADE_INFO_1 structure pointer. If this call returns <b>FALSE</b>, the spooler writes an entry in the event log.

For Windows NT 4.0 and previous, when the spooler calls <b>DrvUpgradePrinter</b>, it supplies a DRIVER_UPGRADE_INFO_1 structure pointer for <i>pDriverUpgradeInfo</i>. If the function returns <b>FALSE</b>, the spooler writes an entry in the event log.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff548522">DRIVER_UPGRADE_INFO_1</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548527">DRIVER_UPGRADE_INFO_2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548564">DrvPrinterEvent</a>
 

 

