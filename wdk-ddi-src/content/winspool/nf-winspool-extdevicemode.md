---
UID: NF:winspool.ExtDeviceMode
title: ExtDeviceMode function
author: windows-driver-content
description: The ExtDeviceMode function is provided only for compatibility with 16-bit applications.
old-location: print\extdevicemode.htm
old-project: print
ms.assetid: dade9d25-7143-4566-adc1-0c97cb508c07
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: ExtDeviceMode, ExtDeviceMode function [Print Devices], print.extdevicemode, spoolfnc_56c49c94-99f4-43b9-90eb-189041a1dd3a.xml, winspool/ExtDeviceMode
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: winspool.h
req.include-header: Winspool.h
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
-	ExtDeviceMode
product: Windows
targetos: Windows
req.typenames: BIDI_TYPE
req.product: Windows 10 or later.
---

# ExtDeviceMode function


## -description


The <b>ExtDeviceMode</b> function is provided only for compatibility with 16-bit applications. Printer drivers without this requirement should instead use the <b>DocumentProperties</b> function, which is described in the Microsoft Windows SDK documentation.

The <b>ExtDeviceMode</b> function retrieves or modifies printer initialization information for a given graphics driver, or displays a driver-supplied printer-configuration property sheet for the specified printer.


## -syntax


````
LONG ExtDeviceMode(
  _In_opt_ HWND       hWnd,
  _In_opt_ HANDLE     hInst,
  _Inout_  LPDEVMODEA pDevModeOutput,
  _In_opt_ LPSTR      pDeviceName,
  _In_opt_ LPSTR      pPort,
  _In_opt_ LPDEVMODEA pDevModeInput,
  _In_opt_ LPSTR      pProfile,
           DWORD      fMode
);
````


## -parameters




### -param hWnd [in, optional]

Handle to the parent window for the printer-configuration property sheet.


### -param hInst [in, optional]


      Not used. Handle to the module instance of the device driver. 


### -param pDevModeOutput [in, out]

Pointer to the DEVMODE structure that receives the printer configuration data supplied in the buffer pointed to by the <i>pDevModeInput</i> parameter. 


### -param pDeviceName [in, optional]

Pointer to a NULL-terminated string that contains the name of the device for which the printer configuration property sheet is displayed.


### -param pPort [in, optional]

Pointer to a NULL-terminated string that contains the name of the port to which the device is connected, such as LPT1.


### -param pDevModeInput [in, optional]

Pointer to the DEVMODE structure that the operating system uses to initialize the property sheet fields. 

This parameter is used only if the DM_IN_BUFFER flag is set in the <i>fMode</i> parameter. If DM_IN_BUFFER is not set, the operating system uses the printer's default DEVMODE structure.


### -param pProfile [in, optional]


      Not used. Pointer to a NULL-terminated string that contains the name of the initialization file in which initialization information is recorded and read from. 


### -param fMode

Specifies the operations that the function performs. If this parameter is zero, the <b>ExtDeviceMode</b> function returns the number of bytes required by the printer driver's DEVMODE structure. Otherwise, this parameter can be set to one or more of the following flag values.

<table>
<tr>
<th>Flag</th>
<th>Meaning</th>
</tr>
<tr>
<td>
DM_COPY

</td>
<td>
Write the driver's current settings to the DEVMODE structure pointed to by the <i>pDevModeOutput</i> parameter. The calling application must allocate a buffer large enough to contain the information. If this flag is not set, <i>pDevModeOutput</i> can be <b>NULL</b>.

</td>
</tr>
<tr>
<td>
DM_IN_BUFFER

</td>
<td>
Merge the printer driver's current print settings with the settings in the DEVMODE structure pointed to by the <i>pDevModeInput</i> parameter. This occurs before prompting, copying, or updating. The function updates the structure only for those members specified by the DEVMODE structure's <b>dmFields</b> member. In cases of conflict during the merge, the settings in the DEVMODE structure pointed to by <i>pDevModeInput</i> override the printer driver's current print settings.

</td>
</tr>
<tr>
<td>
DM_UPDATE

</td>
<td>
Display a property sheet to allow the user to modify printer properties, and then write the driver's current "per user" settings to the user's hive in the registry. 

</td>
</tr>
</table>
 


## -returns



If the <i>wMode</i> parameter is zero, the function returns the size, in bytes, of the DEVMODE structure required to contain the printer-driver initialization data. Note that this value can be larger than the size of a DEVMODE structure if the printer driver appends private data to the structure. If the function displays the initialization-dialog box, the return value is either IDOK or IDCANCEL, depending on which button the user chose. If the function does not display the dialog box and was successful, the return value is IDOK. The return value is less than zero if the function failed. 




## -remarks



The <b>ExtDeviceMode</b> function calls the <b>DocumentProperties</b> function (described in the Windows SDK documentation) to display a property sheet that allows a user to select printer options such as paper size, paper orientation, and output quality. Printer drivers written for Windows 3.x and Windows 9x use this function. 



