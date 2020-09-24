---
UID: NF:wiamicro.MicroEntry
title: MicroEntry function (wiamicro.h)
description: The MicroEntry function responds to commands sent by the WIA Flatbed driver.
old-location: image\microentry.htm
tech.root: image
ms.assetid: 3e0c51af-ceb9-4c06-ab6a-ccc468997fdd
ms.date: 05/03/2018
keywords: ["MicroEntry function"]
ms.keywords: MicroDrv_04aa15b3-5e4d-453d-b41a-a4de3c1228f7.xml, MicroEntry, MicroEntry function [Imaging Devices], image.microentry, wiamicro/MicroEntry
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
req.lib: 
req.dll: 
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - MicroEntry
 - wiamicro/MicroEntry
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - wiamicro.h
api_name:
 - MicroEntry
---

# MicroEntry function


## -description

The **MicroEntry** function responds to commands sent by the WIA Flatbed driver.

## -parameters

### -param lCommand

Specifies a command issued to the microdriver by the WIA Flatbed driver.

### -param pValue 

[in, out]
Points to a [VAL](./ns-wiamicro-val.md) structure that is used to pass information between the WIA Flatbed driver and the microdriver.

## -returns

If the function succeeds, it returns S_OK. If a passed command is not supported,  the function returns E_NOTIMPL. For any error, error information must be put in the **lVal** member of the VAL structure pointed to by *pValue*.

## -remarks

This function performs many different tasks, depending on the command passed in the *lCommand* parameter. See the [WIA Microdriver Commands](/windows-hardware/drivers/image/wia-microdriver-commands) reference section for a list of these commands.

Two structures are passed to the function. A [VAL](./ns-wiamicro-val.md) structure is passed in the *pValue* pointer, and the **pScanInfo** member of the VAL structure points to a [SCANINFO](./ns-wiamicro-_scaninfo.md) structure. The VAL structure is used to pass information between the WIA Flatbed Driver and the microdriver. The SCANINFO structure is used to store and communicate parameters of a scan data acquisition. Many of the commands passed to this function set values in the SCANINFO structure.

## -see-also

[SCANINFO](./ns-wiamicro-_scaninfo.md)

[VAL](./ns-wiamicro-val.md)

[WIA Microdriver Commands](/windows-hardware/drivers/image/wia-microdriver-commands)

[WIA Microdriver Structures](../_image/index.md)