---
UID: NS:winspool._DRIVER_INFO_8A
title: "_DRIVER_INFO_8A"
author: windows-driver-content
description: The DRIVER_INFO_8 structure contains printer driver information.
old-location: print\driver_info_8.htm
tech.root: print
ms.assetid: 95f62d57-300a-4179-868b-f14f29c58b4d
ms.author: windowsdriverdev
ms.date: 4/20/2018
ms.keywords: "*LPDRIVER_INFO_8A, *PDRIVER_INFO_8A, DRIVER_INFO_8, DRIVER_INFO_8 structure [Print Devices], DRIVER_INFO_8A, LPDRIVER_INFO_8, LPDRIVER_INFO_8 structure pointer [Print Devices], PDRIVER_INFO_8, PDRIVER_INFO_8 structure pointer [Print Devices], _DRIVER_INFO_8A, print.driver_info_8, print_ticket-package_dba844e8-6e97-4eaf-8de4-1003562e01d5.xml, winspool/DRIVER_INFO_8, winspool/LPDRIVER_INFO_8, winspool/PDRIVER_INFO_8"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: winspool.h
req.include-header: Winspool.h
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	winspool.h
api_name:
-	DRIVER_INFO_8
product:
- Windows
targetos: Windows
req.typenames: DRIVER_INFO_8A, *PDRIVER_INFO_8A, *LPDRIVER_INFO_8A
---

# _DRIVER_INFO_8A structure


## -description


The DRIVER_INFO_8 structure contains printer driver information. 


## -struct-fields




### -field cVersion

This member specifies the operating system version for which the driver was written. Currently it can be the following.

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
3

</td>
<td>
Driver for Microsoft Windows 2000, XP, or Windows Vista.

</td>
</tr>
</table>
 


### -field pName

A pointer to a null-terminated string that specifies the name of the driver (for example, QMS 810). 


### -field pEnvironment

A pointer to a null-terminated string that specifies the environment for which the driver was written (for example, Microsoft Windows NT x86, Windows NT R4000, Windows NT Alpha_AXP, or Windows 4.0). 


### -field pDriverPath

A pointer to a null-terminated string that specifies a file name or a full path and file name for the file that contains the device driver (for example, C:\DRIVERS\Pscript.dll). 


### -field pDataFile

A pointer to a null-terminated string that specifies a file name or a full path and file name for the file that contains driver data (for example, C:\DRIVERS\Qms810.ppd).


### -field pConfigFile

A pointer to a null-terminated string that specifies a file name or a full path and file name for the device driver's configuration dynamic-link library (for example, C:\DRIVERS\Pscrptui.dll). 


### -field pHelpFile

A pointer to a null-terminated string that specifies a file name or a full path and file name for the device driver's help file (for example, C:\DRIVERS\Pscrptui.hlp). 


### -field pDependentFiles

Pointer to a Multi-SZ string that contains the names of the files on which the driver depends. The file names are stored as a contiguous series of zero-terminated strings followed by an empty string. For example, Pscript.dll\0QMS810.ppd\0Pscriptui.dll\0Pscriptui.hlp\0Pstest.txt\0\0, where \0 represents the terminating null character.


### -field pMonitorName

A pointer to a null-terminated string that specifies a language monitor (for example, "PJL monitor"). This member can be <b>NULL</b> and should be specified only for printers capable of bidirectional communication. 


### -field pDefaultDataType

A pointer to a null-terminated string that specifies the default data type of the print job (for example, "EMF"). 


### -field pszzPreviousNames

A pointer to a null-terminated string that specifies any previous printer driver names that are compatible with this driver (for example, OldName1\0OldName2\0\0). 


### -field ftDriverDate

The date of the driver package, as coded in the driver files.


### -field dwlDriverVersion

The version number of the driver. This comes out of the version structure of the driver. 


### -field pszMfgName

A pointer to a null-terminated string that specifies the manufacturer's name.


### -field pszOEMUrl

A pointer to a null-terminated string that specifies the URL for the manufacturer. 


### -field pszHardwareID

A pointer to a null-terminated string that specifies the hardware ID for the printer driver. 


### -field pszProvider

A pointer to a null-terminated string that specifies the provider of the printer driver (for example, "Microsoft Windows 2000").


### -field pszPrintProcessor

A pointer to a null-terminated string that specifies the name of the print processor associated with the printer driver.


### -field pszVendorSetup

A pointer to a null-terminated string that specifies the vendor setup DLL and entry point for vendor setup that is associated with the printer driver.


### -field pszzColorProfiles

A pointer to a null-terminated string that specifies all color profiles that are associated with the printer driver.


### -field pszInfPath

A pointer to a null-terminated string that specifies the path of the INF file inside the driver store from which the printer driver was installed. Must be <b>NULL</b> if using the <a href="http://msdn.microsoft.com/library/windows/desktop/dd183346(v=vs.85).aspx">AddPrinterDriver</a> or <a href="http://msdn.microsoft.com/library/windows/desktop/dd183347(v=vs.85).aspx">AddPrinterDriverEx</a> functions with DRIVER_INFO_8.


### -field dwPrinterDriverAttributes

This member specifies printer driver related properties. Must be zero if using the <a href="http://msdn.microsoft.com/library/windows/desktop/dd183346(v=vs.85).aspx">AddPrinterDriver</a> or <a href="http://msdn.microsoft.com/library/windows/desktop/dd183347(v=vs.85).aspx">AddPrinterDriverEx</a> functions with DRIVER_INFO_8. The following table shows the flags that have been defined for the <i>dwPrinterDriverAttributes</i> parameter.
	  

<table>
<tr>
<th>Flag name/value</th>
<th>Meaning</th>
<th>Minimum OS</th>
</tr>
<tr>
<td>
PRINTER_DRIVER_PACKAGE_AWARE

0x00000001

</td>
<td>The printer driver is part of a driver package.</td>
<td>Windows Vista</td>
</tr>
<tr>
<td>
PRINTER_DRIVER_XPS

0x00000002

</td>
<td>The printer driver supports the Microsoft XPS format described in the <a href="http://msdn.microsoft.com/windows/hardware/gg463373.aspx">XML Paper Specification: Overview</a>, and also in <a href="http://msdn.microsoft.com/library/e81cbc09-ab05-4a32-ae4a-8ec57b436c43(v=prot.10)">Product Behavior, section <27></a>.</td>
<td>
Windows 8

Windows Server 2012

</td>
</tr>
<tr>
<td>
PRINTER_DRIVER_SANDBOX_ENABLED

0x00000004

</td>
<td>The printer driver is compatible with <a href="http://msdn.microsoft.com/library/831cd729-be7c-451e-b729-bd8d84ce4d24(v=prot.10)">printer driver isolation</a>. For more information, see <a href="http://msdn.microsoft.com/library/e81cbc09-ab05-4a32-ae4a-8ec57b436c43(v=prot.10)">Product Behavior, section <28></a>.</td>
<td>
Windows 7

Windows Server 2008 R2

</td>
</tr>
<tr>
<td>
PRINTER_DRIVER_CLASS

0x00000008

</td>
<td>The printer driver is a <a href="http://msdn.microsoft.com/library/831cd729-be7c-451e-b729-bd8d84ce4d24(v=prot.10)">class printer driver</a>.</td>
<td>
Windows 8

Windows Server 2012

</td>
</tr>
<tr>
<td>
PRINTER_DRIVER_DERIVED

0x00000010

</td>
<td>The printer driver is a <a href="http://msdn.microsoft.com/library/831cd729-be7c-451e-b729-bd8d84ce4d24(v=prot.10)">derived printer driver</a>.</td>
<td>
Windows 8

Windows Server 2012

</td>
</tr>
<tr>
<td>
PRINTER_DRIVER_NOT_SHAREABLE

0x00000020

</td>
<td>Printers using this printer driver cannot be shared.</td>
<td>
Windows 8

Windows Server 2012

</td>
</tr>
<tr>
<td>
PRINTER_DRIVER_CATEGORY_FAX

0x00000040

</td>
<td>The printer driver is intended for use with <a href="http://msdn.microsoft.com/library/831cd729-be7c-451e-b729-bd8d84ce4d24(v=prot.10)">fax printers</a>.</td>
<td>
Windows 8

Windows Server 2012

</td>
</tr>
<tr>
<td>
PRINTER_DRIVER_CATEGORY_FILE

0x00000080

</td>
<td>The printer driver is intended for use with <a href="http://msdn.microsoft.com/library/831cd729-be7c-451e-b729-bd8d84ce4d24(v=prot.10)">file printers</a>.</td>
<td>
Windows 8

Windows Server 2012

</td>
</tr>
<tr>
<td>
PRINTER_DRIVER_CATEGORY_VIRTUAL

0x00000100

</td>
<td>The printer driver is intended for use with <a href="http://msdn.microsoft.com/library/831cd729-be7c-451e-b729-bd8d84ce4d24(v=prot.10)">virtual printers</a>.</td>
<td>
Windows 8

Windows Server 2012

</td>
</tr>
<tr>
<td>
PRINTER_DRIVER_CATEGORY_SERVICE

0x00000200

</td>
<td>The printer driver is intended for use with <a href="http://msdn.microsoft.com/library/831cd729-be7c-451e-b729-bd8d84ce4d24(v=prot.10)">service printers</a>.</td>
<td>
Windows 8

Windows Server 2012

</td>
</tr>
<tr>
<td>
PRINTER_DRIVER_SOFT_RESET_REQUIRED

0x00000400

</td>
<td>Printers that use this printer driver should follow the guidelines outlined in <a href="http://go.microsoft.com/fwlink/p/?linkid=517016">USB Device Class Definition</a>. For more information, see <a href="http://msdn.microsoft.com/library/e81cbc09-ab05-4a32-ae4a-8ec57b436c43(v=prot.10)">Product Behavior, section <36></a></td>
<td>
Windows 8

Windows Server 2012

</td>
</tr>
<tr>
<td>
PRINTER_DRIVER_CATEGORY_3D

0x00001000

</td>
<td>
The printer driver is intended for use with 3D printers.

</td>
<td>
Windows 8

Windows Server 2012

</td>
</tr>
</table>
 


### -field pszzCoreDriverDependencies

A pointer to a null-terminated string that contains all the core printer driver dependencies for the driver package that are defined by <i>pszInfPath</i>. Must be <b>NULL</b> if using the <a href="http://msdn.microsoft.com/library/windows/desktop/dd183346(v=vs.85).aspx">AddPrinterDriver</a> or <a href="http://msdn.microsoft.com/library/windows/desktop/dd183347(v=vs.85).aspx">AddPrinterDriverEx</a> functions with DRIVER_INFO_8.


### -field ftMinInboxDriverVerDate

The earliest allowed date of any drivers that shipped with Windows and on which this driver depends.


### -field dwlMinInboxDriverVerVersion

The earliest allowed version of any drivers that shipped with Windows and on which this driver depends.


## -remarks



The strings for these members are contained in the INF file that is used to add the driver.

If you call <b>AddPrinterDriver</b> or <b>AddPrinterDriverEx</b> with Level not equal to 6 or 8, and then you call <b>GetPrinterDriver</b> or <b>EnumPrinterDrivers</b> with Level equal to 6 or 8, the <b>DRIVER_INFO_8</b> structure is returned with pszMfgName, pszOEMUrl, pszHardwareID, and pszProvider set to <b>NULL</b>, dwlDriverVersion set to zero, and ftDriverDate set to (0,0).

This structure is available in Windows Vista.



