---
UID: NS:storport._SRBEX_DATA
title: _SRBEX_DATA (storport.h)
description: The SRBEX_DATA structure is the generalized format for containing extended SRB data.
old-location: storage\srbex_data.htm
tech.root: storage
ms.assetid: 15FB9877-6339-484B-83D5-6AD44EEE1D6E
ms.date: 03/29/2018
ms.keywords: "*PSRBEX_DATA, PSRBEX_DATA, PSRBEX_DATA structure pointer [Storage Devices], SRBEX_DATA, SRBEX_DATA structure [Storage Devices], SrbExDataTypeBidirectional, SrbExDataTypeIoInfo, SrbExDataTypePnp, SrbExDataTypePower, SrbExDataTypeScsiCdb16, SrbExDataTypeScsiCdb32, SrbExDataTypeScsiCdbVar, SrbExDataTypeUnknown, SrbExDataTypeWmi, _SRBEX_DATA, storage.srbex_data, storport/PSRBEX_DATA, storport/SRBEX_DATA"
ms.topic: struct
f1_keywords:
 - "storport/SRBEX_DATA"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Storport.h
api_name:
- SRBEX_DATA
product:
- Windows
targetos: Windows
req.typenames: SRBEX_DATA, *PSRBEX_DATA
---

# _SRBEX_DATA structure


## -description


The <b>SRBEX_DATA</b> structure is the generalized format for containing extended SRB data.
<div class="alert"><b>Note</b>  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

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
The SRB extended data is formatted as an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/srb/ns-srb-_srbex_data_bidirectional">SRBEX_DATA_BIDIRECTIONAL</a> structure.

</td>
</tr>
<tr>
<td width="40%"><a id="SrbExDataTypeScsiCdb16"></a><a id="srbexdatatypescsicdb16"></a><a id="SRBEXDATATYPESCSICDB16"></a><dl>
<dt><b>SrbExDataTypeScsiCdb16</b></dt>
</dl>
</td>
<td width="60%">
The SRB extended data is formatted as an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/srb/ns-srb-_srbex_data_scsi_cdb16">SRBEX_DATA_SCSI_CDB16</a> structure.

</td>
</tr>
<tr>
<td width="40%"><a id="SrbExDataTypeScsiCdb32"></a><a id="srbexdatatypescsicdb32"></a><a id="SRBEXDATATYPESCSICDB32"></a><dl>
<dt><b>SrbExDataTypeScsiCdb32</b></dt>
</dl>
</td>
<td width="60%">
The SRB extended data is formatted as an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/srb/ns-srb-_srbex_data_scsi_cdb32">SRBEX_DATA_SCSI_CDB32</a> structure.

</td>
</tr>
<tr>
<td width="40%"><a id="SrbExDataTypeScsiCdbVar"></a><a id="srbexdatatypescsicdbvar"></a><a id="SRBEXDATATYPESCSICDBVAR"></a><dl>
<dt><b>SrbExDataTypeScsiCdbVar</b></dt>
</dl>
</td>
<td width="60%">
The SRB extended data is formatted as an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/srb/ns-srb-_srbex_data_scsi_cdb_var">SRBEX_DATA_SCSI_CDB_VAR</a> structure.

</td>
</tr>
<tr>
<td width="40%"><a id="SrbExDataTypeWmi"></a><a id="srbexdatatypewmi"></a><a id="SRBEXDATATYPEWMI"></a><dl>
<dt><b>SrbExDataTypeWmi</b></dt>
</dl>
</td>
<td width="60%">
The SRB extended data is formatted as an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/srb/ns-srb-_srbex_data_wmi">SRBEX_DATA_WMI</a> structure.

</td>
</tr>
<tr>
<td width="40%"><a id="SrbExDataTypePower"></a><a id="srbexdatatypepower"></a><a id="SRBEXDATATYPEPOWER"></a><dl>
<dt><b>SrbExDataTypePower</b></dt>
</dl>
</td>
<td width="60%">
The SRB extended data is formatted as an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/srb/ns-srb-_srbex_data_power">SRBEX_DATA_POWER</a> structure.

</td>
</tr>
<tr>
<td width="40%"><a id="SrbExDataTypePnp"></a><a id="srbexdatatypepnp"></a><a id="SRBEXDATATYPEPNP"></a><dl>
<dt><b>SrbExDataTypePnp</b></dt>
</dl>
</td>
<td width="60%">
The SRB extended data is formatted as an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/srb/ns-srb-_srbex_data_pnp">SRBEX_DATA_PNP</a> structure.

</td>
</tr>
<tr>
<td width="40%"><a id="SrbExDataTypeIoInfo"></a><a id="srbexdatatypeioinfo"></a><a id="SRBEXDATATYPEIOINFO"></a><dl>
<dt><b>SrbExDataTypeIoInfo</b></dt>
</dl>
</td>
<td width="60%">
The SRB extended data is formatted as an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/srb/ns-srb-_srbex_data_io_info">SRBEX_DATA_IO_INFO</a> structure.

</td>
</tr>
</table>
 


### -field Length

Length of the SRB data, in bytes, present  in the <b>Data</b> member.


### -field Data

The extended SRB data block contents.


## -remarks



The SRB extended data is present when the <b>SrbExDataOffset</b> array in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/srb/ns-srb-_storage_request_block">STORAGE_REQUEST_BLOCK</a> structure contains valid offset locations.  A storage driver initially references a memory offset location contained in <b>SrbExDataOffset</b> as an <b>SRBEX_DATA</b> structure. A pointer to the data block is then cast to the appropriate structure type based on the data type value in the <b>Type</b> member.

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

    function = (SrbEx->Function == SRB_FUNCTION_STORAGE_REQUEST_BLOCK) ? SrbEx->SrbFunction : Srb->Function;

    switch (function)
    {
        case SRB_FUNCTION_PNP:
        {
            STOR_PNP_ACTION PnpAction;
            BOOLEAN ForAdapter;

            if (SrbEx->Function == SRB_FUNCTION_STORAGE_REQUEST_BLOCK)
            {
                PSRBEX_DATA_PNP SrbExDataPnp = NULL;

                SrbExData = (PSRBEX_DATA) ((PUCHAR)SrbEx + SrbEx->SrbExDataOffset[0]);
                if (SrbExData->Type == SrbExDataTypePnp)
                {
                    SrbExDataPnp = (PSRBEX_DATA_PNP) SrbExData;
                    ForAdapter = (SrbExDataPnp->SrbPnPFlags == SRB_PNP_FLAGS_ADAPTER_REQUEST);
                    PnpAction = SrbExDataPnp->PnPAction;
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

                ForAdapter = (PnpSrb->SrbPnPFlags == SRB_PNP_FLAGS_ADAPTER_REQUEST);
                PnpAction = PnpSrb->PnPAction;
           }

           if (ForAdapter)
           {
               switch (PnpAction)
               {
                   case StorRemoveDevice:
                       //
                       // ...
                       //
                       Srb->SrbStatus = SRB_STATUS_SUCCESS;
                       break;

                   default:
                       Srb->SrbStatus = SRB_STATUS_INVALID_REQUEST;
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




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/srb/ns-srb-_srbex_data_bidirectional">SRBEX_DATA_BIDIRECTIONAL</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/srb/ns-srb-_srbex_data_io_info">SRBEX_DATA_IO_INFO</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/srb/ns-srb-_srbex_data_pnp">SRBEX_DATA_PNP</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/srb/ns-srb-_srbex_data_power">SRBEX_DATA_POWER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/srb/ns-srb-_srbex_data_scsi_cdb16">SRBEX_DATA_SCSI_CDB16</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/srb/ns-srb-_srbex_data_scsi_cdb32">SRBEX_DATA_SCSI_CDB32</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/srb/ns-srb-_srbex_data_scsi_cdb_var">SRBEX_DATA_SCSI_CDB_VAR</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/srb/ns-srb-_srbex_data_wmi">SRBEX_DATA_WMI</a>
 

 

