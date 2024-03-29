---
UID: NF:wudfusb.IWDFUsbRequestCompletionParams.GetDeviceControlTransferParameters
title: IWDFUsbRequestCompletionParams::GetDeviceControlTransferParameters (wudfusb.h)
description: The GetDeviceControlTransferParameters method retrieves parameters that are associated with the completion of a device I/O control request.
old-location: wdf\iwdfusbrequestcompletionparams_getdevicecontroltransferparameters.htm
tech.root: wdf
ms.date: 02/26/2018
keywords: ["IWDFUsbRequestCompletionParams::GetDeviceControlTransferParameters"]
ms.keywords: GetDeviceControlTransferParameters, GetDeviceControlTransferParameters method, GetDeviceControlTransferParameters method,IWDFUsbRequestCompletionParams interface, IWDFUsbRequestCompletionParams interface,GetDeviceControlTransferParameters method, IWDFUsbRequestCompletionParams.GetDeviceControlTransferParameters, IWDFUsbRequestCompletionParams::GetDeviceControlTransferParameters, UMDFRequestObjectRef_b645716e-2ec3-45f3-a3b2-199374aadef8.xml, umdf.iwdfusbrequestcompletionparams_getdevicecontroltransferparameters, wdf.iwdfusbrequestcompletionparams_getdevicecontroltransferparameters, wudfusb/IWDFUsbRequestCompletionParams::GetDeviceControlTransferParameters
req.header: wudfusb.h
req.include-header: Wudfusb.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 1.5
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: Unavailable in UMDF 2.0 and later.
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: WUDFx.dll
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - IWDFUsbRequestCompletionParams::GetDeviceControlTransferParameters
 - wudfusb/IWDFUsbRequestCompletionParams::GetDeviceControlTransferParameters
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - WUDFx.dll
api_name:
 - IWDFUsbRequestCompletionParams::GetDeviceControlTransferParameters
---

# IWDFUsbRequestCompletionParams::GetDeviceControlTransferParameters


## -description

<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>GetDeviceControlTransferParameters</b> method retrieves parameters that are associated with the completion of a device I/O control request.

## -parameters

### -param ppMemory [out, optional]


A pointer to a variable that receives a pointer to the <a href="/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdfmemory">IWDFMemory</a> interface, for access to the buffer for the device I/O control request. This parameter is optional and can be <b>NULL</b>.

### -param pLengthTransferred [out, optional]


A pointer to a variable that receives the size, in bytes, of transferred data. This parameter is optional and can be <b>NULL</b>.

### -param pOffset [out, optional]


A pointer to a variable that receives the offset, in bytes, into the buffer for the I/O control request. This parameter is optional and can be <b>NULL</b>.

### -param pSetupPacket [out, optional]


A pointer that receives the WinUsb setup packet for the control transfer. This pointer is a PWINUSB_SETUP_PACKET data type that is defined as PVOID. This parameter is optional and can be <b>NULL</b>.

## -see-also

<a href="/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdfmemory">IWDFMemory</a>



<a href="/windows-hardware/drivers/ddi/wudfusb/nn-wudfusb-iwdfusbrequestcompletionparams">IWDFUsbRequestCompletionParams</a>

