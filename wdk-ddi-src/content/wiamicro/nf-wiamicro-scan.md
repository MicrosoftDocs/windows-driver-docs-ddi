---
UID: NF:wiamicro.Scan
title: Scan function (wiamicro.h)
description: The Scan function reads data from the device and returns the data to the WIA Flatbed driver.
old-location: image\scan.htm
tech.root: image
ms.assetid: 057b548a-d9e4-4db4-b34f-d867b7be3971
ms.date: 05/03/2018
ms.keywords: MicroDrv_ab289619-86b7-47fd-a5f5-e8533da4db31.xml, Scan, Scan function [Imaging Devices], image.scan, wiamicro/Scan
ms.topic: function
f1_keywords:
 - "wiamicro/Scan"
req.header: wiamicro.h
req.include-header: Wiamicro.h
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- Scan
product:
- Windows
targetos: Windows
req.typenames: 
---

# Scan function

## -description

The **Scan** function reads data from the device and returns the data to the WIA Flatbed driver. 

## -parameters

### -param pScanInfo [in, out]

Specifies the [SCANINFO](https://docs.microsoft.com/windows-hardware/drivers/ddi/wiamicro/ns-wiamicro-_scaninfo) structure that represents the microdriver's settings. This is stored by the WIA Flatbed driver to guarantee that the settings between the microdriver and the WIA Flatbed driver are synchronized. 

### -param lPhase

Specifies the scan phase requested. This parameter can be set to one of the following values.

| Value | Meaning |
| --- | --- |
| SCAN_FIRST | This signals the first phase of the scan. The microdriver performs three tasks: it initializes the device, it uses the data in the [SCANINFO](https://docs.microsoft.com/windows-hardware/drivers/ddi/wiamicro/ns-wiamicro-_scaninfo) structure to set up the scan (for example, set the resolution, the start position, the width and the height on the device), and it starts the scan. Data must be returned from this call. Data must be put into the buffer pointed to by *pBuffer* and the *pReceived* parameter must be set to the amount of data put in the buffer. |
| SCAN_NEXT | This will be repeatedly called during the data transfer. Data should be put into the buffer pointed to by *pBuffer* and the *pReceived* parameter must be set to the amount of data put in the buffer. |
| SCAN_FINISHED | This will be called at the end of the scan to terminate the scanning process. No data should be transferred. SCAN_FINISHED will always be called even if the user cancels the scan. The microdriver should stop transferring data and the scanner should be reset so that it is ready for the next scan.<br>The data returned from this function should be in raw format without any header. The data can be either packed or planar, aligned or unaligned, and in RGB or BGR order. Set the **RawDataFormat**, **RawPixelOrder**, and **bNeedDataAlignment** members of the [SCANINFO](https://docs.microsoft.com/windows-hardware/drivers/ddi/wiamicro/ns-wiamicro-_scaninfo) structure appropriately in response to the CMD_INITIALIZE command. |

### -param pBuffer [out]

Specifies the buffer that will be filled with scanned data by the microdriver. This buffer is allocated by the WIA Flatbed Driver and is guaranteed to be at least *lLength* bytes in length.

### -param lLength

Specifies the requested amount of data that will be scanned. The microdriver must never overfill the buffer pointed to by *pBuffer*.

### -param plReceived

#### - pReceived [out]

Specifies the amount of data actually scanned into *pBuffer*. This value should never exceed the value of *lLength*, but can be less.

## -returns

If the function succeeds, it returns S_OK. If the function fails, it returns a standard COM error code.

## -see-also

[SCANINFO](https://docs.microsoft.com/windows-hardware/drivers/ddi/wiamicro/ns-wiamicro-_scaninfo)

[WIA Microdriver Commands](https://docs.microsoft.com/windows-hardware/drivers/image/wia-microdriver-commands)

[WIA Microdriver Structures](https://docs.microsoft.com/windows-hardware/drivers/ddi/_image/index)
