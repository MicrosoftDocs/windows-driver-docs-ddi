---
UID: NF:wiamicro.Scan
title: Scan function
author: windows-driver-content
description: The Scan function reads data from the device and returns the data to the WIA Flatbed driver.
old-location: image\scan.htm
old-project: image
ms.assetid: 057b548a-d9e4-4db4-b34f-d867b7be3971
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: MicroDrv_ab289619-86b7-47fd-a5f5-e8533da4db31.xml, image.scan, wiamicro/Scan, Scan, Scan function [Imaging Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wiamicro.h
req.include-header: Wiamicro.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Me and in Windows XP and later versions of the Windows operating systems.
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	Scan
product: Windows
targetos: Windows
req.typenames: "*LPDEVICEDIALOGDATA2, *PDEVICEDIALOGDATA2, DEVICEDIALOGDATA2"
req.product: Windows 10 or later.
---

# Scan function


## -description


The <b>Scan</b> function reads data from the device and returns the data to the WIA Flatbed driver. 


## -syntax


````
WIAMICRO_API HRESULT Scan(
  _Inout_ PSCANINFO pScanInfo,
          LONG      lPhase,
  _Out_   PBYTE     pBuffer,
          LONG      lLength,
  _Out_   LONG      *pReceived
);
````


## -parameters




#### - pScanInfo [in, out]

Specifies the <a href="..\wiamicro\ns-wiamicro-_scaninfo.md">SCANINFO</a> structure that represents the microdriver's settings. This is stored by the WIA Flatbed driver to guarantee that the settings between the microdriver and the WIA Flatbed driver are synchronized. 


#### - lPhase

Specifies the scan phase requested. This parameter can be set to one of the following values.
<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
SCAN_FIRST

</td>
<td>
This signals the first phase of the scan. The microdriver performs three tasks: it initializes the device, it uses the data in the <a href="..\wiamicro\ns-wiamicro-_scaninfo.md">SCANINFO</a> structure to set up the scan (for example, set the resolution, the start position, the width and the height on the device), and it starts the scan. Data must be returned from this call. Data must be put into the buffer pointed to by <i>pBuffer</i> and the <i>pReceived</i> parameter must be set to the amount of data put in the buffer.

</td>
</tr>
<tr>
<td>
SCAN_NEXT

</td>
<td>
This will be repeatedly called during the data transfer. Data should be put into the buffer pointed to by <i>pBuffer</i> and the <i>pReceived</i> parameter must be set to the amount of data put in the buffer.

</td>
</tr>
<tr>
<td>
SCAN_FINISHED

</td>
<td>
This will be called at the end of the scan to terminate the scanning process. No data should be transferred. SCAN_FINISHED will always be called even if the user cancels the scan. The microdriver should stop transferring data and the scanner should be reset so that it is ready for the next scan.

The data returned from this function should be in raw format without any header. The data can be either packed or planar, aligned or unaligned, and in RGB or BGR order. Set the <b>RawDataFormat</b>, <b>RawPixelOrder</b>, and <b>bNeedDataAlignment</b> members of the <a href="..\wiamicro\ns-wiamicro-_scaninfo.md">SCANINFO</a> structure appropriately in response to the CMD_INITIALIZE command.

</td>
</tr>
</table> 


#### - pBuffer [out]

Specifies the buffer that will be filled with scanned data by the microdriver. This buffer is allocated by the WIA Flatbed Driver and is guaranteed to be at least <i>lLength</i> bytes in length.


#### - lLength

Specifies the requested amount of data that will be scanned. The microdriver must never overfill the buffer pointed to by <i>pBuffer</i>.


### -param plReceived

TBD



#### - pReceived [out]

Specifies the amount of data actually scanned into <i>pBuffer</i>. This value should never exceed the value of <i>lLength</i>, but can be less.


## -returns


If the function succeeds, it returns S_OK. If the function fails, it returns a standard COM error code.



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff552714">WIA Microdriver Commands</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff552722">WIA Microdriver Structures</a>

<a href="..\wiamicro\ns-wiamicro-_scaninfo.md">SCANINFO</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [image\image]:%20Scan function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

