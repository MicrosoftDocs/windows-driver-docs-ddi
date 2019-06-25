---
UID: NF:sercx.SerCx2CustomReceiveTransactionCreate
title: SerCx2CustomReceiveTransactionCreate function (sercx.h)
description: The SerCx2CustomReceiveTransactionCreate method creates a custom-receive-transaction object, which version 2 of the serial framework extension (SerCx2) uses to perform custom-receive transactions.
old-location: serports\sercx2customreceivetransactioncreate.htm
tech.root: serports
ms.assetid: 3E01268B-69DB-4713-841B-8B27D24F8431
ms.date: 04/23/2018
ms.keywords: 2/SerCx2CustomReceiveTransactionCreate, SerCx2CustomReceiveTransactionCreate, SerCx2CustomReceiveTransactionCreate method [Serial Ports], serports.sercx2customreceivetransactioncreate
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
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- 2.0\Sercx.h
api_name:
- SerCx2CustomReceiveTransactionCreate
product:
- Windows
targetos: Windows
req.typenames: 
---

# SerCx2CustomReceiveTransactionCreate function


## -description


The <b>SerCx2CustomReceiveTransactionCreate</b> method creates a custom-receive-transaction object, which version 2 of the serial framework extension (SerCx2) uses to perform custom-receive transactions.


## -parameters




### -param CustomReceive [in]

A <a href="https://docs.microsoft.com/windows-hardware/drivers/serports/sercx2-object-handles">SERCX2CUSTOMRECEIVE</a> handle to a custom-receive object. The serial controller driver previously called the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/sercx/nf-sercx-sercx2customreceivecreate">SerCx2CustomReceiveCreate</a> method to create this object.


### -param CustomReceiveTransactionConfig [in]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/sercx/ns-sercx-_sercx2_custom_receive_transaction_config">SERCX2_CUSTOM_RECEIVE_TRANSACTION_CONFIG</a> structure. Before calling this method, the caller must call the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/sercx/nf-sercx-sercx2_custom_receive_transaction_config_init">SERCX2_CUSTOM_RECEIVE_TRANSACTION_CONFIG_INIT</a> function to initialize the structure. This structure contains pointers to a set of event callback routines that are implemented by the serial controller driver. SerCx2 calls these functions to do an I/O transaction that uses the custom data-transfer mechanism to read data received by the serial controller.


### -param Attributes [in]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfobject/ns-wdfobject-_wdf_object_attributes">WDF_OBJECT_ATTRIBUTES</a> structure that describes the attributes to assign to the new custom-receive-transaction object. Before calling this method, the caller must call the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfobject/nf-wdfobject-wdf_object_attributes_init">WDF_OBJECT_ATTRIBUTES_INIT</a> function to initialize the structure. This parameter is optional and can be specified as WDF_NO_OBJECT_ATTRIBUTES if the serial controller driver does not need to assign attributes to the object. For more information, see Remarks.


### -param CustomReceiveTransaction [out]

A pointer to a location to which this method writes a <a href="https://docs.microsoft.com/windows-hardware/drivers/serports/sercx2-object-handles">SERCX2CUSTOMRECEIVETRANSACTION</a> handle to the newly created custom-receive-transaction object. SerCx2 and the serial controller driver use this handle in subsequent calls to refer to this object.


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
The <i>CustomReceiveTransactionConfig</i>-><b>Size</b> value does not equal <b>sizeof</b>(<b>SERCX2_CUSTOM_RECEIVE_TRANSACTION_CONFIG</b>).

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
A parameter value is not valid. The caller must supply valid <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/sercx/nc-sercx-evt_sercx2_custom_receive_transaction_start">EvtSerCx2CustomReceiveTransactionStart</a> and <a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/dn265203(v=vs.85)">EvtSerCx2CustomReceiveTransactionQueryProgress</a> function pointers.

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

As an option, a serial controller driver can use the <i>Attributes</i> parameter to create a context for the custom-receive object, and to supply pointers to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfobject/nc-wdfobject-evt_wdf_object_context_cleanup">EvtCleanupCallback</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfobject/nc-wdfobject-evt_wdf_object_context_destroy">EvtDestroyCallback</a> functions that are called to prepare the object for deletion. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfobject/ns-wdfobject-_wdf_object_attributes">WDF_OBJECT_ATTRIBUTES</a>.

If the <i>Attributes</i> parameter points to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfobject/ns-wdfobject-_wdf_object_attributes">WDF_OBJECT_ATTRIBUTES</a> structure, the caller must not overwrite the values that the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfobject/nf-wdfobject-wdf_object_attributes_init">WDF_OBJECT_ATTRIBUTES_INIT</a> initialization function writes to the <b>ParentObject</b>, <b>ExecutionLevel</b>, and <b>SynchronizationScope</b> members of this structure.

If the specified combination of implemented callback functions is not valid, the <b>SerCx2CustomReceiveTransactionCreate</b> call fails and returns STATUS_INVALID_PARAMETER.

For more information about creating custom-receive-transaction objects, see <a href="https://docs.microsoft.com/windows-hardware/drivers/serports/sercx2-object-handles">SERCX2CUSTOMRECEIVETRANSACTION</a>. For more information about custom-receive transactions, see <a href="https://docs.microsoft.com/previous-versions/dn265314(v=vs.85)">SerCx2 Custom-Receive Transactions</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfobject/nc-wdfobject-evt_wdf_object_context_cleanup">EvtCleanupCallback</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfobject/nc-wdfobject-evt_wdf_object_context_destroy">EvtDestroyCallback</a>



<a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/dn265203(v=vs.85)">EvtSerCx2CustomReceiveTransactionQueryProgress</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/sercx/nc-sercx-evt_sercx2_custom_receive_transaction_start">EvtSerCx2CustomReceiveTransactionStart</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/serports/sercx2-object-handles">SERCX2CUSTOMRECEIVE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/serports/sercx2-object-handles">SERCX2CUSTOMRECEIVETRANSACTION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/sercx/ns-sercx-_sercx2_custom_receive_transaction_config">SERCX2_CUSTOM_RECEIVE_TRANSACTION_CONFIG</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/sercx/nf-sercx-sercx2_custom_receive_transaction_config_init">SERCX2_CUSTOM_RECEIVE_TRANSACTION_CONFIG_INIT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/sercx/nf-sercx-sercx2customreceivecreate">SerCx2CustomReceiveCreate</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfobject/ns-wdfobject-_wdf_object_attributes">WDF_OBJECT_ATTRIBUTES</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfobject/nf-wdfobject-wdf_object_attributes_init">WDF_OBJECT_ATTRIBUTES_INIT</a>
 

 

