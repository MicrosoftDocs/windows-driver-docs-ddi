---
UID: NC:dispmprt.DXGKCB_MIRACAST_SEND_MESSAGE
title: DXGKCB_MIRACAST_SEND_MESSAGE
author: windows-driver-content
description: Sends an asynchronous message to the user-mode display driver.
old-location: display\dxgkcbmiracastsendmessage.htm
old-project: display
ms.assetid: E8C3B9E3-854C-488D-809B-0F0893591352
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.dxgkcbmiracastsendmessage, DxgkCbMiracastSendMessage callback function [Display Devices], DxgkCbMiracastSendMessage, DXGKCB_MIRACAST_SEND_MESSAGE, DXGKCB_MIRACAST_SEND_MESSAGE, dispmprt/DxgkCbMiracastSendMessage
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: dispmprt.h
req.include-header: Dispmprt.h
req.target-type: Desktop
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: Windows Server 2012 R2
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	Dispmprt.h
apiname:
-	DxgkCbMiracastSendMessage
product: Windows
targetos: Windows
req.typenames: "*PSYMBOL_INFO_EX, SYMBOL_INFO_EX"
---

# DXGKCB_MIRACAST_SEND_MESSAGE callback


## -description


Sends an asynchronous message to the user-mode display driver.


## -prototype


````
DXGKCB_MIRACAST_SEND_MESSAGE DxgkCbMiracastSendMessage;

NTSTATUS* DxgkCbMiracastSendMessage(
  _In_     HANDLE                                MiracastHandle,
  _In_     ULONG                                 InputBufferSize,
  _In_     VOID                                  *pInputBuffer,
  _In_     ULONG                                 OutBufferSize,
  _Out_    VOID                                  *pOutputBuffer,
  _In_opt_ DXGKCB_MIRACAST_SEND_MESSAGE_CALLBACK pCallback,
  _In_opt_ PVOID                                 pCallbackContext
)
{ ... }
````


## -parameters




### -param MiracastHandle [in]

A driver-supplied handle to the Miracast display device. This handle was originally passed in the <b>MiracastHandle</b> member of the <a href="..\dispmprt\ns-dispmprt-_dxgk_miracast_display_callbacks.md">DXGK_MIRACAST_DISPLAY_CALLBACKS</a> structure in a call to the <a href="..\dispmprt\nc-dispmprt-dxgkddi_miracast_create_context.md">DxgkDdiMiracastCreateContext</a> function.


### -param InputBufferSize [in]

The size, in bytes, of the input buffer pointed to by <i>pInputBuffer</i>.


### -param *pInputBuffer [in]

A pointer to the input buffer. <i>InputBufferSize</i> specifies the size of the buffer.

See Remarks for more info about the input buffer.


### -param OutputBufferSize



### -param *pOutputBuffer [out]

A pointer to the output buffer. <i>OutBufferSize</i> specifies the size of the buffer.

See Remarks for more info about the output buffer.


### -param pCallback [in, optional]

An optional pointer, supplied by the display miniport driver, to the <a href="..\dispmprt\nc-dispmprt-dxgkcb_miracast_send_message_callback.md">DxgkCbMiracastSendMessageCallback</a> callback function.

If the display miniport driver supplies the pointer to <a href="..\dispmprt\nc-dispmprt-dxgkcb_miracast_send_message_callback.md">DxgkCbMiracastSendMessageCallback</a>, then after the user-mode driver handles the message, the operating system sends a message to the user-mode driver asynchronously by calling <b>DxgkCbMiracastSendMessageCallback</b>.

See Return value and Remarks sections for more about calls to <a href="..\dispmprt\nc-dispmprt-dxgkcb_miracast_send_message_callback.md">DxgkCbMiracastSendMessageCallback</a>.


### -param pCallbackContext [in, optional]

An optional driver-supplied pointer to the driver-supplied callback context. The operating system passes this context to the driver-supplied callback routine after the operation has completed.


#### - OutBufferSize [in]

The size, in bytes, of the output buffer pointed to by <i>pOutputBuffer</i>.


## -returns


Returns <b>STATUS_PENDING</b> if it successfully delivers the message. Otherwise, it returns one of the error codes that are defined in Ntstatus.h.

If the display miniport driver needs to know the status of message handling in user mode, it should supply the <a href="..\dispmprt\nc-dispmprt-dxgkcb_miracast_send_message_callback.md">DxgkCbMiracastSendMessageCallback</a> function in the <i>pCallback</i> parameter and check the return status in that function's <i>pIoStatusBlock</i> parameter.



## -remarks


If the display miniport driver supplies the <i>pInputBuffer</i> and <i>pOutputBuffer</i> buffers, it is the driver’s responsibility to hold these two buffers until the <a href="..\dispmprt\nc-dispmprt-dxgkcb_miracast_send_message_callback.md">DxgkCbMiracastSendMessageCallback</a> function is called. Otherwise, a random memory corruption issue can be created.

If the driver supplies the <a href="..\dispmprt\nc-dispmprt-dxgkcb_miracast_send_message_callback.md">DxgkCbMiracastSendMessageCallback</a> in the <i>pCallback</i> parameter, it's possible that <b>DxgkCbMiracastSendMessageCallback</b> will return before <b>DxgkCbMiracastSendMessage</b> returns.
<h3><a id="Example_calling_sequence"></a><a id="example_calling_sequence"></a><a id="EXAMPLE_CALLING_SEQUENCE"></a>Example calling sequence</h3>Here's example code that shows how to use this function:
<div class="code"><span codelanguage="ManagedCPlusPlus"><table>
<tr>
<th>C++</th>
</tr>
<tr>
<td>
<pre>typedef struct _CALLBACK_CONTEXT
{
    UCHAR InputBuffer[INPUT_BUFFER_SIZE];
    UCHAR OutputBuffer[OUTPUT_BUFFER_SIZE];
} CALLBACK_CONTEXT, *PCALLBACK_CONTEXT;

...

_IRQL_requires_(PASSIVE_LEVEL)
VOID
DriverCallbackFunction(
    _In_ PVOID Context,
    _In_ PIO_STATUS_BLOCK pIoStatusBlock
    )
{
    PCALLBACK_CONTEXT CallbackContex = (PCALLBACK_CONTEXT)Context;

    ExFreePool(CallbackContex);
}

...

    CallbackContex = (PCALLBACK_CONTEXT)ExAllocatePoolWithTag(
                            PagedPool,
                            sizeof(CALLBACK_CONTEXT),
                            DRIVER_TAG);

    if (CallbackContex == NULL)
    {
        return STATUS_NO_MEMORY;
    }

    RtlZeroMemory(CallbackContex, sizeof(CALLBACK_CONTEXT));

    CallbackContex-&gt;InputBuffer[0] = 0xaa;
    CallbackContex-&gt;InputBuffer[1] = 0x55;

    Status = 
      pDeviceContext-&gt;MiracastCallbacks.DxgkCbMiracastSendMessage(
          pDeviceContext-&gt;MiracastCallbacks.MiracastHandle,
          sizeof(CallbackContex-&gt;InputBuffer),
          CallbackContex-&gt;InputBuffer,
          sizeof(CallbackContex-&gt;OutputBuffer),
          CallbackContext-&gt;OutputBuffer,
          &amp;DriverCallbackFunction,
          CallbackContex);
</pre>
</td>
</tr>
</table></span></div>


## -see-also

<a href="..\dispmprt\nc-dispmprt-dxgkddi_miracast_create_context.md">DxgkDdiMiracastCreateContext</a>

<a href="..\dispmprt\ns-dispmprt-_dxgk_miracast_display_callbacks.md">DXGK_MIRACAST_DISPLAY_CALLBACKS</a>

<a href="..\dispmprt\nc-dispmprt-dxgkcb_miracast_send_message_callback.md">DxgkCbMiracastSendMessageCallback</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKCB_MIRACAST_SEND_MESSAGE callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

