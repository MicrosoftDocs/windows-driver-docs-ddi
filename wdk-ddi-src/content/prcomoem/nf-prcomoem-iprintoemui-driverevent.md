---
UID: NF:prcomoem.IPrintOemUI.DriverEvent
title: IPrintOemUI::DriverEvent
author: windows-driver-content
description: The printer driver's DrvDriverEvent function calls a user interface plug-in's IPrintOemUI::DriverEvent method for additional processing of printer driver events.
old-location: print\iprintoemui_driverevent.htm
tech.root: print
ms.assetid: aacddaea-3a6f-4018-92ac-fe4aa2ddabd3
ms.date: 04/20/2018
ms.keywords: DriverEvent, DriverEvent method [Print Devices], DriverEvent method [Print Devices],IPrintOemUI interface, IPrintOemUI interface [Print Devices],DriverEvent method, IPrintOemUI.DriverEvent, IPrintOemUI::DriverEvent, prcomoem/IPrintOemUI::DriverEvent, print.iprintoemui_driverevent, print_unidrv-pscript_ui_797a9e90-b481-4bae-9bfd-e00e362e9a7a.xml
ms.topic: method
req.header: prcomoem.h
req.include-header: Prcomoem.h
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
-	COM
api_location:
-	prcomoem.h
api_name:
-	IPrintOemUI.DriverEvent
product:
- Windows
targetos: Windows
req.typenames: 
---

# IPrintOemUI::DriverEvent


## -description


The printer driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff548551">DrvDriverEvent</a> function calls a user interface plug-in's <code>IPrintOemUI::DriverEvent</code> method for additional processing of printer driver events.


## -parameters




### -param dwDriverEvent

Caller-supplied bit flag indicating the event that has occurred. Valid flags are listed in the following table.

<table>
<tr>
<th>Flag</th>
<th>Definition</th>
</tr>
<tr>
<td>
DRIVER_EVENT_DELETE

</td>
<td>
The driver is being removed.

</td>
</tr>
<tr>
<td>
DRIVER_EVENT_INITIALIZE

</td>
<td>
The driver has just been installed.

</td>
</tr>
</table>
 


### -param dwLevel

Caller-supplied value indicating the type of structure pointed to by the <i>pDriverInfo</i> parameter, as indicated in the following table.

<table>
<tr>
<th><i>dwLevel</i> Value</th>
<th>Structure pointed to by <i>pDriverInfo</i></th>
</tr>
<tr>
<td>
1

</td>
<td>
DRIVER_INFO_1

</td>
</tr>
<tr>
<td>
2

</td>
<td>
DRIVER_INFO_2

</td>
</tr>
<tr>
<td>
3

</td>
<td>
DRIVER_INFO_3

</td>
</tr>
</table>
 

The DRIVER_INFO_<i>N</i> structures are described in the Microsoft Windows SDK documentation.


### -param pDriverInfo

Caller-supplied pointer to a structure whose type is identified by the <i>dwLevel</i> parameter.


### -param lParam

Caller-supplied flags. See the following Remarks section.


## -returns



The method must return one of the following values.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>S_OK</b></dt>
</dl>
</td>
<td width="60%">
The operation succeeded.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_FAIL</b></dt>
</dl>
</td>
<td width="60%">
The operation failed.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_NOTIMPL</b></dt>
</dl>
</td>
<td width="60%">
The method is not implemented.

</td>
</tr>
</table>
 




## -remarks



A user interface plug-in's <code>IPrintOemUI::DriverEvent</code> method performs the same types of operations as the <b>DrvDriverEvent</b> function that is exported by user-mode printer interface DLLs. For information about driver events and how they should be processed, see the description of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff548551">DrvDriverEvent</a> function.

If you provide a user interface plug-in, the printer driver's <b>DrvDriverEvent</b> function calls the <code>IPrintOemUI::DriverEvent</code> method. The <b>DrvDriverEvent</b> function performs its own processing for the specified event, and then calls the <code>IPrintOemUI::DriverEvent</code> method to handle additional processing of the event.

If <code>IPrintOemUI::DriverEvent</code> methods are exported by multiple user interface plug-ins, the methods are called in the order that the plug-ins are specified for installation.

For more information about creating and installing user interface plug-ins, see <a href="https://msdn.microsoft.com/b7761209-1f6f-4288-af47-4ed855c2e629">Customizing Microsoft's Printer Drivers</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff548551">DrvDriverEvent</a>



<a href="https://msdn.microsoft.com/0ef635dd-9598-4356-94fc-7e5237df9bd9">IPrintOemUI</a>
 

 

