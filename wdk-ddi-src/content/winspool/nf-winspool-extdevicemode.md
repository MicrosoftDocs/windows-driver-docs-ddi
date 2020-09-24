---
UID: NF:winspool.ExtDeviceMode
title: ExtDeviceMode function (winspool.h)
description: The ExtDeviceMode function is provided only for compatibility with 16-bit applications.
old-location: print\extdevicemode.htm
tech.root: print
ms.assetid: dade9d25-7143-4566-adc1-0c97cb508c07
ms.date: 09/21/2020
keywords: ["ExtDeviceMode function"]
ms.keywords: ExtDeviceMode, ExtDeviceMode function [Print Devices], print.extdevicemode, spoolfnc_56c49c94-99f4-43b9-90eb-189041a1dd3a.xml, winspool/ExtDeviceMode
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
targetos: Windows
req.typenames: 
f1_keywords:
 - ExtDeviceMode
 - winspool/ExtDeviceMode
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - WinSpool.drv
api_name:
 - ExtDeviceMode
---

# ExtDeviceMode function

## -description

The **ExtDeviceMode** function is provided only for compatibility with 16-bit applications. Printer drivers without this requirement should instead use the **DocumentProperties** function, which is described in the Microsoft Windows SDK documentation.

The **ExtDeviceMode** function retrieves or modifies printer initialization information for a given graphics driver, or displays a driver-supplied printer-configuration property sheet for the specified printer.

## -parameters

### -param hWnd

[in, optional]

Handle to the parent window for the printer-configuration property sheet.

### -param hInst

[in, optional]

Not used. Handle to the module instance of the device driver.

### -param pDevModeOutput

[in, out]

Pointer to the DEVMODE structure that receives the printer configuration data supplied in the buffer pointed to by the *pDevModeInput* parameter.

### -param pDeviceName

[in, optional]
Pointer to a NULL-terminated string that contains the name of the device for which the printer configuration property sheet is displayed.

### -param pPort

[in, optional]

Pointer to a NULL-terminated string that contains the name of the port to which the device is connected, such as LPT1.

### -param pDevModeInput

[in, optional]

Pointer to the DEVMODE structure that the operating system uses to initialize the property sheet fields.

This parameter is used only if the DM_IN_BUFFER flag is set in the *fMode* parameter. If DM_IN_BUFFER is not set, the operating system uses the printer's default DEVMODE structure.

### -param pProfile

[in, optional]

Not used. Pointer to a NULL-terminated string that contains the name of the initialization file in which initialization information is recorded and read from.

### -param fMode

Specifies the operations that the function performs. If this parameter is zero, the **ExtDeviceMode** function returns the number of bytes required by the printer driver's DEVMODE structure. Otherwise, this parameter can be set to one or more of the following flag values.

| Flag | Description |
|--|--|
| DM_COPY | Write the driver's current settings to the DEVMODE structure pointed to by the *pDevModeOutput* parameter. The calling application must allocate a buffer large enough to contain the information. If this flag is not set, *pDevModeOutput* can be **NULL**. |
| DM_IN_BUFFER | Merge the printer driver's current print settings with the settings in the DEVMODE structure pointed to by the *pDevModeInput* parameter. This occurs before prompting, copying, or updating. The function updates the structure only for those members specified by the DEVMODE structure's **dmFields** member. In cases of conflict during the merge, the settings in the DEVMODE structure pointed to by *pDevModeInput* override the printer driver's current print settings. |
| DM_UPDATE | Display a property sheet to allow the user to modify printer properties, and then write the driver's current "per user" settings to the user's hive in the registry. |

## -returns

If the *wMode* parameter is zero, the function returns the size, in bytes, of the DEVMODE structure required to contain the printer-driver initialization data. Note that this value can be larger than the size of a DEVMODE structure if the printer driver appends private data to the structure. If the function displays the initialization-dialog box, the return value is either IDOK or IDCANCEL, depending on which button the user chose. If the function does not display the dialog box and was successful, the return value is IDOK. The return value is less than zero if the function failed.

## -remarks

The **ExtDeviceMode** function calls the **DocumentProperties** function (described in the Windows SDK documentation) to display a property sheet that allows a user to select printer options such as paper size, paper orientation, and output quality. Printer drivers written for Windows 3.x and Windows 9x use this function.
