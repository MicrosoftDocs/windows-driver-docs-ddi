---
UID: NS:wiamicro.VAL
title: VAL (wiamicro.h)
description: The VAL structure is used by the microdriver and WIA Flatbed driver to pass information between each other.
old-location: image\val.htm
tech.root: image
ms.assetid: 9c9cf520-3249-4c1e-9d0d-e07f7127117e
ms.date: 05/03/2018
keywords: ["VAL structure"]
ms.keywords: "*PVAL, MicroDrv_397b66fc-2f8e-434e-88ac-24b5cdd415d5.xml, PVAL, PVAL structure pointer [Imaging Devices], VAL, VAL structure [Imaging Devices], image.val, wiamicro/PVAL, wiamicro/VAL"
req.header: wiamicro.h
req.include-header: Wiamicro.h
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
targetos: Windows
req.typenames: VAL, *PVAL
f1_keywords:
 - VAL
 - wiamicro/VAL
 - PVAL
 - wiamicro/PVAL
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - wiamicro.h
api_name:
 - VAL
---

# VAL structure


## -description

The VAL structure is used by the microdriver and WIA Flatbed driver to pass information between each other.

## -struct-fields

### -field lVal

Specifies a command value to return to the WIA Flatbed driver. See [WIA Microdriver Commands](https://docs.microsoft.com/windows-hardware/drivers/image/wia-microdriver-commands) for a list of available commands for this parameter.

### -field dblVal

Specifies a command value to return to the WIA Flatbed driver. See [WIA Microdriver Commands](https://docs.microsoft.com/windows-hardware/drivers/image/wia-microdriver-commands) for a list of available commands for this parameter.

### -field pGuid

Points to the GUID of the pressed button. If no button was pressed, this member points to GUID_NULL.

### -field pScanInfo

Points to a [SCANINFO](https://docs.microsoft.com/windows-hardware/drivers/ddi/wiamicro/ns-wiamicro-_scaninfo) structure.

### -field handle

Points to a ShutDown event handle that will be signaled by the WIA Flatbed Driver when the driver is being unloaded or shut down.

### -field ppButtonNames

Specifies the address of a pointer to an array of button names.

### -field pHandle

Points to an event handle.

### -field lReserved

Reserved. Do not use.

### -field szVal

Specifies the device name in ASCII form. If needed for interrupt checking, the microdriver can use this name to pass to [CreateFile](https://docs.microsoft.com/windows/win32/api/fileapi/nf-fileapi-createfilea) in order to obtain a file handle to the device.

