---
UID: NF:winddiui.DrvUpgradePrinter
title: DrvUpgradePrinter function
author: windows-driver-content
description: A printer interface DLL's DrvUpgradePrinter function is used for updating a printer's registry settings when a new version of the driver is added to a system.
old-location: print\drvupgradeprinter.htm
old-project: print
ms.assetid: 5a8a764d-48bf-48f9-831a-ac22767aeca6
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: ",  , D, DrvUpgradePrinter, DrvUpgradePrinter function [Print Devices], P, U, a, d, e, g, i, n, p, print.drvupgradeprinter, print_interface-graphics_ab060948-18bc-4b0f-a504-320083fcb173.xml, r, t, v, winddiui/DrvUpgradePrinter"
ms.prod: windows-hardware
ms.technology: windows-devices
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	winddiui.h
apiname:
-	DrvUpgradePrinter
product: Windows
targetos: Windows
req.typenames: WINBIO_VERSION, *PWINBIO_VERSION
req.product: Windows 10 or later.
---

# DrvUpgradePrinter function


## -description


A printer interface DLL's <b>DrvUpgradePrinter</b> function is used for updating a printer's registry settings when a new version of the driver is added to a system.


## -syntax


````
BOOL DrvUpgradePrinter(
           DWORD  Level,
  _In_opt_ LPBYTE pDriverUpgradeInfo
);
````


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

<a href="..\winddiui\ns-winddiui-_driver_upgrade_info_1.md">DRIVER_UPGRADE_INFO_1</a>


</td>
</tr>
<tr>
<td>
2

</td>
<td>

<a href="..\winddiui\ns-winddiui-_driver_upgrade_info_2.md">DRIVER_UPGRADE_INFO_2</a>


</td>
</tr>
</table>
 


### -param pDriverUpgradeInfo [in, optional]

Caller-supplied pointer to a structure whose type is identified by <i>dwLevel</i>. 


## -returns



If the operation succeeds, the function should return <b>TRUE</b>; otherwise, it should call SetLastError to set an error code and return <b>FALSE</b>.




## -remarks



A <a href="https://msdn.microsoft.com/2a8cf38f-8e27-4e08-9c0f-5d1a4cd854ac">printer interface DLL</a> can optionally provide a <b>DrvUpgradePrinter</b> function. If it does, the spooler calls it for every printer when the printer driver is copied onto the system. This occurs when a system is upgraded from one operating system release to the next, or when an application updates a printer driver by calling the Win32 <b>AddPrinterDriver</b> function.

Often, a new driver version requires registry settings that are different from those of the old version. The <b>DrvUpgradePrinter</b> function's purpose is to update the registry so it is compatible with the driver. For more information about storing printer information in the registry, see <a href="..\winddiui\nf-winddiui-drvprinterevent.md">DrvPrinterEvent</a>.

For Windows 2000 and later, when the spooler calls <b>DrvUpgradePrinter</b>, it supplies a DRIVER_UPGRADE_INFO_2 structure pointer for <i>pDriverUpgradeInfo</i>. If the function returns <b>FALSE</b>, the spooler calls the function again, this time specifying a DRIVER_UPGRADE_INFO_1 structure pointer. If this call returns <b>FALSE</b>, the spooler writes an entry in the event log.

For Windows NT 4.0 and previous, when the spooler calls <b>DrvUpgradePrinter</b>, it supplies a DRIVER_UPGRADE_INFO_1 structure pointer for <i>pDriverUpgradeInfo</i>. If the function returns <b>FALSE</b>, the spooler writes an entry in the event log.




## -see-also

<a href="..\winddiui\nf-winddiui-drvprinterevent.md">DrvPrinterEvent</a>



<a href="..\winddiui\ns-winddiui-_driver_upgrade_info_2.md">DRIVER_UPGRADE_INFO_2</a>



<a href="..\winddiui\ns-winddiui-_driver_upgrade_info_1.md">DRIVER_UPGRADE_INFO_1</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20DrvUpgradePrinter function%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

