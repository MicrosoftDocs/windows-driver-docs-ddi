---
UID: NF:sercx.SerCx2CustomReceiveTransactionCreate
title: SerCx2CustomReceiveTransactionCreate function
author: windows-driver-content
description: The SerCx2CustomReceiveTransactionCreate method creates a custom-receive-transaction object, which version 2 of the serial framework extension (SerCx2) uses to perform custom-receive transactions.
old-location: serports\sercx2customreceivetransactioncreate.htm
old-project: serports
ms.assetid: 3E01268B-69DB-4713-841B-8B27D24F8431
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: 2/SerCx2CustomReceiveTransactionCreate, serports.sercx2customreceivetransactioncreate, SerCx2CustomReceiveTransactionCreate, SerCx2CustomReceiveTransactionCreate method [Serial Ports]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: sercx.h
req.include-header: 
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 8.1.
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	2.0\Sercx.h
apiname:
-	SerCx2CustomReceiveTransactionCreate
product: Windows
targetos: Windows
req.typenames: SERCX_STATUS, *PSERCX_STATUS
req.product: Windows 10 or later.
---

# SerCx2CustomReceiveTransactionCreate function


## -description


The <b>SerCx2CustomReceiveTransactionCreate</b> method creates a custom-receive-transaction object, which version 2 of the serial framework extension (SerCx2) uses to perform custom-receive transactions.


## -syntax


````
NTSTATUS SerCx2CustomReceiveTransactionCreate(
  [in]  SERCX2CUSTOMRECEIVE                       CustomReceive,
  [in]  PSERCX2_CUSTOM_RECEIVE_TRANSACTION_CONFIG CustomReceiveTransactionConfig,
  [in]  PWDF_OBJECT_ATTRIBUTES                    Attributes,
  [out] SERCX2CUSTOMRECEIVETRANSACTION            *CustomReceiveTransaction
);
````


## -parameters




### -param CustomReceive [in]

A <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/serports/sercx2-object-handles">SERCX2CUSTOMRECEIVE</a> handle to a custom-receive object. The serial controller driver previously called the <a href="..\sercx\nf-sercx-sercx2customreceivecreate.md">SerCx2CustomReceiveCreate</a> method to create this object.


### -param CustomReceiveTransactionConfig [in]

A pointer to a <a href="..\sercx\ns-sercx-_sercx2_custom_receive_transaction_config.md">SERCX2_CUSTOM_RECEIVE_TRANSACTION_CONFIG</a> structure. Before calling this method, the caller must call the <a href="..\sercx\nf-sercx-sercx2_custom_receive_transaction_config_init.md">SERCX2_CUSTOM_RECEIVE_TRANSACTION_CONFIG_INIT</a> function to initialize the structure. This structure contains pointers to a set of event callback routines that are implemented by the serial controller driver. SerCx2 calls these functions to do an I/O transaction that uses the custom data-transfer mechanism to read data received by the serial controller.


### -param Attributes [in]

A pointer to a <a href="..\wdfobject\ns-wdfobject-_wdf_object_attributes.md">WDF_OBJECT_ATTRIBUTES</a> structure that describes the attributes to assign to the new custom-receive-transaction object. Before calling this method, the caller must call the <a href="..\wdfobject\nf-wdfobject-wdf_object_attributes_init.md">WDF_OBJECT_ATTRIBUTES_INIT</a> function to initialize the structure. This parameter is optional and can be specified as WDF_NO_OBJECT_ATTRIBUTES if the serial controller driver does not need to assign attributes to the object. For more information, see Remarks.


### -param CustomReceiveTransaction [out]

A pointer to a location to which this method writes a <a href="https://msdn.microsoft.com/library/windows/hardware/dn265249">SERCX2CUSTOMRECEIVETRANSACTION</a> handle to the newly created custom-receive-transaction object. SerCx2 and the serial controller driver use this handle in subsequent calls to refer to this object.


## -returns



This method returns STATUS_SUCCESS if the call is successful. Possible error return values include the following status codes.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_DEVICE_REQUEST</b></dt>
</dl>
</td>
<td width="60%">
A custom-receive-transaction object already exists from a previous <b>SerCx2CustomReceiveTransactionCreate</b> call.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INFO_LENGTH_MISMATCH</b></dt>
</dl>
</td>
<td width="60%">
The <i>CustomReceiveTransactionConfig</i>-&gt;<b>Size</b> value does not equal <b>sizeof</b>(<b>SERCX2_CUSTOM_RECEIVE_TRANSACTION_CONFIG</b>).

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
A parameter value is not valid. The caller must supply valid <a href="..\sercx\nc-sercx-evt_sercx2_custom_receive_transaction_start.md">EvtSerCx2CustomReceiveTransactionStart</a> and <a href="https://msdn.microsoft.com/B0B08257-E867-4E22-949E-555AD44C2DDE">EvtSerCx2CustomReceiveTransactionQueryProgress</a> function pointers.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
Insufficient resources are available to create the custom-receive-transaction object.

</td>
</tr>
</table>
 




## -remarks



Your serial controller driver can call this method to create a custom-receive-transaction object. SerCx2 uses this object to manage custom-receive transactions, which are I/O transactions that use a custom data-transfer mechanism to read data received by the serial controller.

As an option, a serial controller driver can use the <i>Attributes</i> parameter to create a context for the custom-receive object, and to supply pointers to <a href="..\wdfobject\nc-wdfobject-evt_wdf_object_context_cleanup.md">EvtCleanupCallback</a> and <a href="..\wdfobject\nc-wdfobject-evt_wdf_object_context_destroy.md">EvtDestroyCallback</a> functions that are called to prepare the object for deletion. For more information, see <a href="..\wdfobject\ns-wdfobject-_wdf_object_attributes.md">WDF_OBJECT_ATTRIBUTES</a>.

If the <i>Attributes</i> parameter points to a <a href="..\wdfobject\ns-wdfobject-_wdf_object_attributes.md">WDF_OBJECT_ATTRIBUTES</a> structure, the caller must not overwrite the values that the <a href="..\wdfobject\nf-wdfobject-wdf_object_attributes_init.md">WDF_OBJECT_ATTRIBUTES_INIT</a> initialization function writes to the <b>ParentObject</b>, <b>ExecutionLevel</b>, and <b>SynchronizationScope</b> members of this structure.

If the specified combination of implemented callback functions is not valid, the <b>SerCx2CustomReceiveTransactionCreate</b> call fails and returns STATUS_INVALID_PARAMETER.

For more information about creating custom-receive-transaction objects, see <a href="https://msdn.microsoft.com/library/windows/hardware/dn265249">SERCX2CUSTOMRECEIVETRANSACTION</a>. For more information about custom-receive transactions, see <a href="https://msdn.microsoft.com/29849A8C-6656-444C-BE91-405A4BA2D5B0">SerCx2 Custom-Receive Transactions</a>.




## -see-also

<a href="..\wdfobject\nf-wdfobject-wdf_object_attributes_init.md">WDF_OBJECT_ATTRIBUTES_INIT</a>



<a href="https://msdn.microsoft.com/B0B08257-E867-4E22-949E-555AD44C2DDE">EvtSerCx2CustomReceiveTransactionQueryProgress</a>



<a href="..\sercx\nc-sercx-evt_sercx2_custom_receive_transaction_start.md">EvtSerCx2CustomReceiveTransactionStart</a>



<a href="..\wdfobject\nc-wdfobject-evt_wdf_object_context_destroy.md">EvtDestroyCallback</a>



<a href="..\sercx\nf-sercx-sercx2customreceivecreate.md">SerCx2CustomReceiveCreate</a>



<a href="..\wdfobject\ns-wdfobject-_wdf_object_attributes.md">WDF_OBJECT_ATTRIBUTES</a>



<a href="..\sercx\ns-sercx-_sercx2_custom_receive_transaction_config.md">SERCX2_CUSTOM_RECEIVE_TRANSACTION_CONFIG</a>



<a href="..\wdfobject\nc-wdfobject-evt_wdf_object_context_cleanup.md">EvtCleanupCallback</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn265249">SERCX2CUSTOMRECEIVETRANSACTION</a>



<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/serports/sercx2-object-handles">SERCX2CUSTOMRECEIVE</a>



<a href="..\sercx\nf-sercx-sercx2_custom_receive_transaction_config_init.md">SERCX2_CUSTOM_RECEIVE_TRANSACTION_CONFIG_INIT</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [serports\serports]:%20SerCx2CustomReceiveTransactionCreate method%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

