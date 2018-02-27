---
UID: NS:storport._SRBEX_DATA
title: "_SRBEX_DATA"
author: windows-driver-content
description: The SRBEX_DATA structure is the generalized format for containing extended SRB data.
old-location: storage\srbex_data.htm
old-project: storage
ms.assetid: 15FB9877-6339-484B-83D5-6AD44EEE1D6E
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: "*PSRBEX_DATA, PSRBEX_DATA, PSRBEX_DATA structure pointer [Storage Devices], SRBEX_DATA, SRBEX_DATA structure [Storage Devices], SrbExDataTypeBidirectional, SrbExDataTypeIoInfo, SrbExDataTypePnp, SrbExDataTypePower, SrbExDataTypeScsiCdb16, SrbExDataTypeScsiCdb32, SrbExDataTypeScsiCdbVar, SrbExDataTypeUnknown, SrbExDataTypeWmi, _SRBEX_DATA, storage.srbex_data, storport/PSRBEX_DATA, storport/SRBEX_DATA"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: storport.h
req.include-header: Storport.h, Srb.h, Minitape.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows 8.
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Storport.h
apiname:
-	SRBEX_DATA
product: Windows
targetos: Windows
req.typenames: SRBEX_DATA, *PSRBEX_DATA
req.product: Windows 10 or later.
---

# _SRBEX_DATA structure


## -description


The <b>SRBEX_DATA</b> structure is the generalized format for containing extended SRB data.
<div class="alert"><b>Note</b>  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## -syntax


````
typedef struct _SRBEX_DATA {
  SRBEXDATATYPE Type;
  ULONG         Length;
  UCHAR         Data[ANYSIZE_ARRAY];
} SRBEX_DATA, *PSRBEX_DATA;
````


## -struct-fields




### -field Type

Data type indicator for the extended SRB data structure. The possible values for <b>Type</b> are one of the following.

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%"><a id="SrbExDataTypeUnknown"></a><a id="srbexdatatypeunknown"></a><a id="SRBEXDATATYPEUNKNOWN"></a><dl>
<dt><b>SrbExDataTypeUnknown</b></dt>
</dl>
</td>
<td width="60%">
The SRB extended data type is unknown.

</td>
</tr>
<tr>
<td width="40%"><a id="SrbExDataTypeBidirectional"></a><a id="srbexdatatypebidirectional"></a><a id="SRBEXDATATYPEBIDIRECTIONAL"></a><dl>
<dt><b>SrbExDataTypeBidirectional</b></dt>
</dl>
</td>
<td width="60%">
The SRB extended data is formatted as an <a href="..\storport\ns-storport-_srbex_data_bidirectional.md">SRBEX_DATA_BIDIRECTIONAL</a> structure.

</td>
</tr>
<tr>
<td width="40%"><a id="SrbExDataTypeScsiCdb16"></a><a id="srbexdatatypescsicdb16"></a><a id="SRBEXDATATYPESCSICDB16"></a><dl>
<dt><b>SrbExDataTypeScsiCdb16</b></dt>
</dl>
</td>
<td width="60%">
The SRB extended data is formatted as an <a href="..\storport\ns-storport-_srbex_data_scsi_cdb16.md">SRBEX_DATA_SCSI_CDB16</a> structure.

</td>
</tr>
<tr>
<td width="40%"><a id="SrbExDataTypeScsiCdb32"></a><a id="srbexdatatypescsicdb32"></a><a id="SRBEXDATATYPESCSICDB32"></a><dl>
<dt><b>SrbExDataTypeScsiCdb32</b></dt>
</dl>
</td>
<td width="60%">
The SRB extended data is formatted as an <a href="..\storport\ns-storport-_srbex_data_scsi_cdb32.md">SRBEX_DATA_SCSI_CDB32</a> structure.

</td>
</tr>
<tr>
<td width="40%"><a id="SrbExDataTypeScsiCdbVar"></a><a id="srbexdatatypescsicdbvar"></a><a id="SRBEXDATATYPESCSICDBVAR"></a><dl>
<dt><b>SrbExDataTypeScsiCdbVar</b></dt>
</dl>
</td>
<td width="60%">
The SRB extended data is formatted as an <a href="..\storport\ns-storport-_srbex_data_scsi_cdb_var.md">SRBEX_DATA_SCSI_CDB_VAR</a> structure.

</td>
</tr>
<tr>
<td width="40%"><a id="SrbExDataTypeWmi"></a><a id="srbexdatatypewmi"></a><a id="SRBEXDATATYPEWMI"></a><dl>
<dt><b>SrbExDataTypeWmi</b></dt>
</dl>
</td>
<td width="60%">
The SRB extended data is formatted as an <a href="..\storport\ns-storport-_srbex_data_wmi.md">SRBEX_DATA_WMI</a> structure.

</td>
</tr>
<tr>
<td width="40%"><a id="SrbExDataTypePower"></a><a id="srbexdatatypepower"></a><a id="SRBEXDATATYPEPOWER"></a><dl>
<dt><b>SrbExDataTypePower</b></dt>
</dl>
</td>
<td width="60%">
The SRB extended data is formatted as an <a href="..\storport\ns-storport-_srbex_data_power.md">SRBEX_DATA_POWER</a> structure.

</td>
</tr>
<tr>
<td width="40%"><a id="SrbExDataTypePnp"></a><a id="srbexdatatypepnp"></a><a id="SRBEXDATATYPEPNP"></a><dl>
<dt><b>SrbExDataTypePnp</b></dt>
</dl>
</td>
<td width="60%">
The SRB extended data is formatted as an <a href="..\storport\ns-storport-_srbex_data_pnp.md">SRBEX_DATA_PNP</a> structure.

</td>
</tr>
<tr>
<td width="40%"><a id="SrbExDataTypeIoInfo"></a><a id="srbexdatatypeioinfo"></a><a id="SRBEXDATATYPEIOINFO"></a><dl>
<dt><b>SrbExDataTypeIoInfo</b></dt>
</dl>
</td>
<td width="60%">
The SRB extended data is formatted as an <a href="..\storport\ns-storport-_srbex_data_io_info.md">SRBEX_DATA_IO_INFO</a> structure.

</td>
</tr>
</table>
 


### -field Length

Length of the SRB data, in bytes, present  in the <b>Data</b> member.


### -field Data

The extended SRB data block contents.


## -remarks



The SRB extended data is present when the <b>SrbExDataOffset</b> array in the <a href="..\storport\ns-storport-_storage_request_block.md">STORAGE_REQUEST_BLOCK</a> structure contains valid offset locations.  A storage driver initially references a memory offset location contained in <b>SrbExDataOffset</b> as an <b>SRBEX_DATA</b> structure. A pointer to the data block is then cast to the appropriate structure type based on the data type value in the <b>Type</b> member.

The following example code fragment shows how to access the extended data for the an SRB function of SRB_FUNCTION_PNP.

<div class="code"><span codelanguage="ManagedCPlusPlus"><table>
<tr>
<th>C++</th>
</tr>
<tr>
<td>
<pre>BOOLEAN CheckIo( _In_ PSCSI_REQUEST_BLOCK Srb)
{
    BOOLEAN result = TRUE;
    ULONG function;
    PSTORAGE_REQUEST_BLOCK SrbEx = (PSTORAGE_REQUEST_BLOCK)Srb;
    PSRBEX_DATA SrbExData = NULL;

    function = (SrbEx-&gt;Function == SRB_FUNCTION_STORAGE_REQUEST_BLOCK) ? SrbEx-&gt;SrbFunction : Srb-&gt;Function;

    switch (function)
    {
        case SRB_FUNCTION_PNP:
        {
            STOR_PNP_ACTION PnpAction;
            BOOLEAN ForAdapter;

            if (SrbEx-&gt;Function == SRB_FUNCTION_STORAGE_REQUEST_BLOCK)
            {
                PSRBEX_DATA_PNP SrbExDataPnp = NULL;

                SrbExData = (PSRBEX_DATA) ((PUCHAR)SrbEx + SrbEx-&gt;SrbExDataOffset[0]);
                if (SrbExData-&gt;Type == SrbExDataTypePnp)
                {
                    SrbExDataPnp = (PSRBEX_DATA_PNP) SrbExData;
                    ForAdapter = (SrbExDataPnp-&gt;SrbPnPFlags == SRB_PNP_FLAGS_ADAPTER_REQUEST);
                    PnpAction = SrbExDataPnp-&gt;PnPAction;
                }
                else
                {
                    ForAdapter = FALSE;
                    result = FALSE;
                }
            }
            else
            {
                PSCSI_PNP_REQUEST_BLOCK PnpSrb = (PSCSI_PNP_REQUEST_BLOCK)Srb;

                ForAdapter = (PnpSrb-&gt;SrbPnPFlags == SRB_PNP_FLAGS_ADAPTER_REQUEST);
                PnpAction = PnpSrb-&gt;PnPAction;
           }

           if (ForAdapter)
           {
               switch (PnpAction)
               {
                   case StorRemoveDevice:
                       //
                       // ...
                       //
                       Srb-&gt;SrbStatus = SRB_STATUS_SUCCESS;
                       break;

                   default:
                       Srb-&gt;SrbStatus = SRB_STATUS_INVALID_REQUEST;
                       result = FALSE;
                       break:
            }
        }

        default:
            break; 
    }

    return result;
}</pre>
</td>
</tr>
</table></span></div>



## -see-also

<a href="..\storport\ns-storport-_srbex_data_pnp.md">SRBEX_DATA_PNP</a>



<a href="..\storport\ns-storport-_srbex_data_scsi_cdb_var.md">SRBEX_DATA_SCSI_CDB_VAR</a>



<a href="..\storport\ns-storport-_srbex_data_scsi_cdb32.md">SRBEX_DATA_SCSI_CDB32</a>



<a href="..\storport\ns-storport-_srbex_data_power.md">SRBEX_DATA_POWER</a>



<a href="..\storport\ns-storport-_srbex_data_scsi_cdb16.md">SRBEX_DATA_SCSI_CDB16</a>



<a href="..\storport\ns-storport-_srbex_data_wmi.md">SRBEX_DATA_WMI</a>



<a href="..\storport\ns-storport-_srbex_data_bidirectional.md">SRBEX_DATA_BIDIRECTIONAL</a>



<a href="..\storport\ns-storport-_srbex_data_io_info.md">SRBEX_DATA_IO_INFO</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20SRBEX_DATA structure%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

