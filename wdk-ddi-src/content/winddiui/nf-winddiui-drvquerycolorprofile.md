---
UID: NF:winddiui.DrvQueryColorProfile
title: DrvQueryColorProfile function
author: windows-driver-content
description: The DrvQueryColorProfile function allows a printer interface DLL to specify an ICC profile to use for color management.
old-location: print\drvquerycolorprofile.htm
old-project: print
ms.assetid: f6eec5a1-7d73-415f-84d9-1ec3f512abaf
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: print.drvquerycolorprofile, DrvQueryColorProfile function [Print Devices], print_interface-graphics_fce84759-2add-41bc-b4e5-c2b66e3abf04.xml, DrvQueryColorProfile, winddiui/DrvQueryColorProfile
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
-	DrvQueryColorProfile
product: Windows
targetos: Windows
req.typenames: *PWINBIO_VERSION, WINBIO_VERSION
req.product: Windows 10 or later.
---

# DrvQueryColorProfile function


## -description


The <b>DrvQueryColorProfile</b> function allows a printer interface DLL to specify an ICC profile to use for color management.


## -syntax


````
BOOL DrvQueryColorProfile(
        HANDLE    hPrinter,
  _In_  PDEVMODEW pdevmode,
        ULONG     ulQueryMode,
  _Out_ VOID      *pvProfileData,
  _Out_ ULONG     *pcbProfileData,
  _Out_ FLONG     *pflProfileData
);
````


## -parameters




### -param hPrinter

Caller-supplied printer handle.


### -param pdevmode [in]

Caller-supplied pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff552837">DEVMODEW</a> structure.


### -param ulQueryMode

One of the following caller-supplied bit flags, indicating the type of profile to be specified.
<table>
<tr>
<th>Flag</th>
<th>Definition</th>
</tr>
<tr>
<td>
QCP_DEVICEPROFILE

</td>
<td>
The caller is requesting a device profile.

</td>
</tr>
<tr>
<td>
QCP_SOURCEPROFILE

</td>
<td>
The caller is requesting a source profile.

</td>
</tr>
</table> 


### -param pvProfileData [out]

Caller-supplied pointer to a buffer to receive profile information.


### -param pcbProfileData [out]

Caller-supplied pointer to a value representing the size, in bytes, of the buffer pointed to by <i>pvProfileData</i>.


### -param pflProfileData [out]

One of the following function-supplied bit flags, indicating the type of information the function is returning.
<table>
<tr>
<th>Flag</th>
<th>Definition</th>
</tr>
<tr>
<td>
QCP_PROFILEDISK

</td>
<td>
The function is returning the file name of an ICC profile in the buffer pointed to by <i>pvProfileData</i>.

</td>
</tr>
<tr>
<td>
QCP_PROFILEMEMORY

</td>
<td>
The function is returning profile data in the buffer pointed to by <i>pvProfileData</i>.

</td>
</tr>
</table> 


## -returns


If the operation succeeds, the function returns <b>TRUE</b>; otherwise, it returns <b>FALSE</b>.



## -remarks


A <a href="https://msdn.microsoft.com/2a8cf38f-8e27-4e08-9c0f-5d1a4cd854ac">printer interface DLL</a> can optionally provide a <b>DrvQueryColorProfile</b> function. If the function is provided, GDI calls it if ICM has been enabled for a print job. The function's purpose is to determine and specify an ICC profile that is appropriate for use with the print job.

If a driver's printer interface DLL does not provide a <b>DrvQueryColorProfile</b> function, or if the function returns <b>FALSE</b>, GDI attempts to find a profile. For more information, see <a href="https://msdn.microsoft.com/828b53cd-452a-4c4d-bfbb-45ea674ef49a">Locating ICC Profiles</a>.

If the output buffer size specified by <i>pcbProfileData</i> is too small, the driver should overwrite the size value supplied by <i>pcbProfileData</i> with the required buffer size, call SetLastError(ERROR_INSUFFICIENT_BUFFER), and return <b>FALSE</b>.


