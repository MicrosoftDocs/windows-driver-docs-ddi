---
UID: NA:wia_lh
ms.assetid: 99eafa9d-3584-3ffa-9589-0fb46987965a
ms.author: windowsdriverdev
ms.date: 02/26/18
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
---

# Wia_Lh.h header



This header is used by Imaging devices. For more information, see
- [Imaging devices](../_image/index.md)

Wia_Lh.h contain these programming interfaces:


## Interfaces

| Title   | Description   |
| ---- |:---- |
| [IWiaErrorHandler interface](nn-wia_lh-iwiaerrorhandler.md) | The IWiaErrorHandler interface provides the GetStatusDescription and ReportStatus methods, which enable minidrivers to give users information about status or errors during a data transfer and possibly give an opportunity to recover from errors. |
| [IWiaImageFilter interface](nn-wia_lh-iwiaimagefilter.md) | The IWiaImageFilter interface is an extension interface implemented by image processing filter developers and called by Microsoft Windows Image Acquisition (WIA). |
| [IWiaLog interface](nn-wia_lh-iwialog.md) | The IWiaLog interface provides methods to enable minidrivers to log trace, error, and warning messages to the diagnostic log file Wiaservc.log. |
| [IWiaSegmentationFilter interface](nn-wia_lh-iwiasegmentationfilter.md) | The IWiaSegmentationFilter interface provides the DetectRegions method, which enables minidrivers to detect image subregions on a flatbed scanner's platen. This interface is available in Windows Vista and later. |
| [IWiaTransferCallback interface](nn-wia_lh-iwiatransfercallback.md) | The IWiaTransferCallback interface is implemented by image processing filter developers and called by Microsoft Windows Image Acquisition (WIA). |

## Methods

| Title   | Description   |
| ---- |:---- |
| [IWiaErrorHandler::GetStatusDescription method](nf-wia_lh-iwiaerrorhandler-getstatusdescription.md) | The system UI calls the GetStatusDescription method to provide the user with extra information about an error, if the user requests this information. This method is implemented by a driver's UI extension. |
| [IWiaErrorHandler::ReportStatus method](nf-wia_lh-iwiaerrorhandler-reportstatus.md) | The ReportStatus method displays information about an error or status during a transfer. In some cases this method allows the user to recover from an error. |
| [IWiaImageFilter::FilterPreviewImage method](nf-wia_lh-iwiaimagefilter-filterpreviewimage.md) | The IWiaImageFilter |
| [IWiaImageFilter::InitializeFilter method](nf-wia_lh-iwiaimagefilter-initializefilter.md) | The IWiaImageFilter |
| [IWiaLog::InitializeLog method](nf-wia_lh-iwialog-initializelog.md) | Note that the IWiaLog interface is obsolete for Microsoft Windows XP and later, and is no longer supported. Instead, use the Diagnostic Log Macros.The IWiaLog |
| [IWiaLog::Log method](nf-wia_lh-iwialog-log.md) | The IWiaLog interface is obsolete for Windows XP and later, and is no longer supported. Use the Diagnostic Log Macros instead.The IWiaLog |
| [IWiaLog::hResult method](nf-wia_lh-iwialog-hresult.md) | Note that the IWiaLog interface is obsolete for Microsoft Windows XP and later, and is no longer supported. |
| [IWiaSegmentationFilter::DetectRegions method](nf-wia_lh-iwiasegmentationfilter-detectregions.md) | The IWiaSegmentationFilter |
| [IWiaTransferCallback::GetNextStream method](nf-wia_lh-iwiatransfercallback-getnextstream.md) | The IWiaTransferCallback |
| [IWiaTransferCallback::TransferCallback method](nf-wia_lh-iwiatransfercallback-transfercallback.md) | The IWiaTransferCallback |
