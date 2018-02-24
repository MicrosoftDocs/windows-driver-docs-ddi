---
UID: NF:winddiui.DevQueryPrintEx
title: DevQueryPrintEx function
author: windows-driver-content
description: A printer interface DLL's DevQueryPrintEx function determines if a specified print job is compatible with the printer's current configuration and can therefore be printed.
old-location: print\devqueryprintex.htm
old-project: print
ms.assetid: f4cd0fe6-acdc-43e6-8dd7-7b547b1ec7cc
ms.author: windowsdriverdev
ms.date: 2/21/2018
ms.keywords: print.devqueryprintex, print_interface-graphics_37504c69-c747-4758-928c-1ebd60e64c94.xml, winddiui/DevQueryPrintEx, DevQueryPrintEx function [Print Devices], DevQueryPrintEx
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
req.lib: Winspool.lib
req.dll: WinSpool.drv
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	WinSpool.drv
apiname:
-	DevQueryPrintEx
product: Windows
targetos: Windows
req.typenames: "*PWINBIO_VERSION, WINBIO_VERSION"
req.product: Windows 10 or later.
---

# DevQueryPrintEx function


## -description


A printer interface DLL's <b>DevQueryPrintEx</b> function determines if a specified print job is compatible with the printer's current configuration and can therefore be printed.


## -syntax


````
BOOL DevQueryPrintEx(
  _Inout_ PDEVQUERYPRINT_INFO pDQPInfo
);
````


## -parameters




### -param pDQPInfo [in, out]

Caller-supplied pointer to a <a href="..\winddiui\ns-winddiui-_devqueryprint_info.md">DEVQUERYPRINT_INFO</a> structure.


## -returns



If the print job can be printed, the function should return <b>TRUE</b>; otherwise, it should return <b>FALSE</b>.




## -remarks



Printer interface DLLs must define a <b>DevQueryPrintEx</b> function. The function is called by the print spooler if the <b>Hold Mismatched Documents</b> option is checked on the <b>Advanced</b> page of the printer's property sheet. If the function returns <b>TRUE</b>, the spooler queues the print job for printing. Otherwise, the job is held, under the assumption that the printer will eventually be reconfigured so the job can print.

The received <a href="..\winddiui\ns-winddiui-_devqueryprint_info.md">DEVQUERYPRINT_INFO</a> structure points to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff552837">DEVMODEW</a> structure describing the printer characteristics required by the print job. The <b>DevQueryPrintEx</b> function should first verify that the size and version members of the received DEVMODEW structure are compatible with the driver. Then it should determine if the supplied DEVMODEW contents are compatible with the current printer configuration.

If the job can be printed, the function should just return <b>TRUE</b>. If the job should be held until later, the function should return <b>FALSE</b> after supplying a displayable text string (in the buffer pointed to by the DEVQUERYPRINT_INFO structure's <b>pszErrorStr</b> member) describing the reason the job cannot be printed.

Displayable text strings should be defined as string resources in a resource file.



