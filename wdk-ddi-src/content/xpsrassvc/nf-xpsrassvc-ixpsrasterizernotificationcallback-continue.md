---
UID: NF:xpsrassvc.IXpsRasterizerNotificationCallback.Continue
title: IXpsRasterizerNotificationCallback::Continue (xpsrassvc.h)
description: The Continue method tells the caller (the XPS rasterization service) whether to continue rasterizing the current XPS fixed page.
tech.root: print
ms.date: 03/03/2023
keywords: ["IXpsRasterizerNotificationCallback::Continue"]
ms.keywords: Continue, Continue method [Print Devices], Continue method [Print Devices],IXpsRasterizerNotificationCallback interface, IXpsRasterizerNotificationCallback interface [Print Devices],Continue method, IXpsRasterizerNotificationCallback.Continue, IXpsRasterizerNotificationCallback::Continue, print.ixpsrasterizernotificationcallback_continue, print_xpsrast_f107f6a3-c35f-4ec1-b50f-062852852af6.xml, xpsrassvc/IXpsRasterizerNotificationCallback::Continue
req.header: xpsrassvc.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Supported in Windows 7 and later versions of the Windows operating system.
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
 - IXpsRasterizerNotificationCallback::Continue
 - xpsrassvc/IXpsRasterizerNotificationCallback::Continue
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - xpsrassvc.h
api_name:
 - IXpsRasterizerNotificationCallback::Continue
---

## -description

The **Continue** method tells the caller (the XPS rasterization service) whether to continue rasterizing the current XPS fixed page.

## -returns

**Continue** returns S_OK to enable rasterization to continue. Otherwise, the method returns an error code to abort rasterization. Possible error return values include:

| Return code | Description |
|---|---|
| **HRESULT_FROM_WIN32(ERROR_PRINT_CANCELLED)** | The current print job has been canceled. |

## -remarks

This method is implemented by an XPSDrv filter. During a page rasterization operation, the [XPS rasterization service](/windows-hardware/drivers/print/using-the-xps-rasterization-service) periodically calls this method to determine whether to continue the operation.

To begin a page rasterization operation, the XPSDrv filter calls the [IXpsRasterizer::RasterizeRect](/windows-hardware/drivers/ddi/xpsrassvc/nf-xpsrassvc-ixpsrasterizer-rasterizerect) method. With this call, the filter can, as an option, supply a pointer to an [IXpsRasterizerNotificationCallback](/windows-hardware/drivers/ddi/xpsrassvc/nn-xpsrassvc-ixpsrasterizernotificationcallback) interface instance. If supplied, **RasterizeRect** will periodically call the **Continue** method on this interface during the processing of the **RasterizeRect** call. If **Continue** returns a success code, **RasterizeRect** continues with the rasterization operation in progress. If **Continue** returns an error code, **RasterizeRect** aborts the rasterization operation and returns immediately.

If the user cancels a print job or if an error occurs during the processing of a print job, the pipeline manager calls the XPSDrv filter's [IPrintPipelineFilter::ShutdownOperation](/windows-hardware/drivers/ddi/filterpipeline/nf-filterpipeline-iprintpipelinefilter-shutdownoperation) method to shut down the filter. Typically, the filter can complete the shutdown in a more timely way if it implements the **Continue** method and supplies an **IXpsRasterizerNotificationCallback** pointer to **RasterizeRect**.

For an example implementation of the **Continue** method, see the XpsRasFilter sample in the WDK. This sample is located in the Src\Print\Xpsrasfilter folder in your WDK installation.

## -see-also

[IPrintPipelineFilter::ShutdownOperation](/windows-hardware/drivers/ddi/filterpipeline/nf-filterpipeline-iprintpipelinefilter-shutdownoperation)

[IXpsRasterizer::RasterizeRect](/windows-hardware/drivers/ddi/xpsrassvc/nf-xpsrassvc-ixpsrasterizer-rasterizerect)

[IXpsRasterizerNotificationCallback](/windows-hardware/drivers/ddi/xpsrassvc/nn-xpsrassvc-ixpsrasterizernotificationcallback)
