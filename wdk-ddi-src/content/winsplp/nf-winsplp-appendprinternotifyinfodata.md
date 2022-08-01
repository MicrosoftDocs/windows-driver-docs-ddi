---
UID: NF:winsplp.AppendPrinterNotifyInfoData
title: AppendPrinterNotifyInfoData function (winsplp.h)
description: The print spooler's AppendPrinterNotifyInfoData function adds the contents of a specified PRINTER_NOTIFY_INFO_DATA structure to a specified PRINTER_NOTIFY_INFO structure.
tech.root: print
ms.date: 07/27/2022
keywords: ["AppendPrinterNotifyInfoData function"]
ms.keywords: AppendPrinterNotifyInfoData, AppendPrinterNotifyInfoData function [Print Devices], print.appendprinternotifyinfodata, spoolfnc_cc8f6371-6dea-497e-92db-6cd9e26e7867.xml, winsplp/AppendPrinterNotifyInfoData
req.header: winsplp.h
req.include-header: Winsplp.h
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
req.lib: Spoolss.lib
req.dll: Spoolss.dll
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - AppendPrinterNotifyInfoData
 - winsplp/AppendPrinterNotifyInfoData
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - Spoolss.dll
api_name:
 - AppendPrinterNotifyInfoData
---

## -description

The print spooler's **AppendPrinterNotifyInfoData** function adds the contents of a specified PRINTER_NOTIFY_INFO_DATA structure to a specified PRINTER_NOTIFY_INFO structure.

## -parameters

### -param pInfoDest [in]

Caller-supplied pointer to a **PRINTER_NOTIFY_INFO** structure.

### -param pDataSrc

Caller-supplied pointer to a **PRINTER_NOTIFY_INFO_DATA** structure.

### -param fdwFlags

Caller-supplied flags. The following flag is defined.

**PRINTER_NOTIFY_INFO_DATA_COMPACT**  
If set, the function examines the **Type**, **Field**, and **Id** members of the supplied **PRINTER_NOTIFY_INFO_DATA** structure. If they all match an existing element of the **PRINTER_NOTIFY_INFO_DATA** structure array, the existing element is overwritten with the supplied element. If a match is not found, the function adds the specified structure to the end of the array.

## -returns

If the operation succeeds, the function returns **TRUE**. Otherwise, the function returns **FALSE**. The caller can obtain an error code by calling *GetLastError*.

## -remarks

A print provider's [RefreshPrinterChangeNotification](/previous-versions/ff561930(v=vs.85)) function should call **AppendPrinterNotifyInfoData** as often as necessary to populate a **PRINTER_NOTIFY_INFO_DATA** structure array, after first calling [RouterAllocPrinterNotifyInfo](/windows-hardware/drivers/ddi/winsplp/nf-winsplp-routerallocprinternotifyinfo) to allocate storage for the array and its associated PRINTER_NOTIFY_INFO structure.

Based on whether the PRINTER_NOTIFY_INFO_DATA_COMPACT flag is set, the function either appends the specified **PRINTER_NOTIFY_INFO_DATA** structure to the end of the structure array or overwrites an existing array element. If the structure is appended, the function increments the **PRINTER_NOTIFY_INFO** structure's **Count** member.

If **AppendPrinterNotifyInfoData** detects that the PRINTER_NOTIFY_INFO_DISCARDED flag is set in the specified **PRINTER_NOTIFY_INFO** structure, the function clears all PRINTER_NOTIFY_INFO_DATA structures and sets the error code to ERROR_OUT_OF_STRUCTURES.

If **NULL** is specified for *pInfoDataSrc*, **AppendPrinterNotifyInfoData** sets the PRINTER_NOTIFY_INFO_DISCARDED flag in the specified **PRINTER_NOTIFY_INFO** structure, clears all **PRINTER_NOTIFY_INFO_DATA** structures, and sets the error code to ERROR_OUT_OF_STRUCTURES.

(For more information about the PRINTER_NOTIFY_INFO_DISCARDED flag, see the description of FindNextPrinterChangeNotification in the Windows SDK documentation.)

For additional information, see [Supporting Printer Change Notifications](/windows-hardware/drivers/print/supporting-printer-change-notifications).

## -see-also

[RefreshPrinterChangeNotification](/previous-versions/ff561930(v=vs.85))

[RouterAllocPrinterNotifyInfo](/windows-hardware/drivers/ddi/winsplp/nf-winsplp-routerallocprinternotifyinfo)
