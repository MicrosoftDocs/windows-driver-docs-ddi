---
UID: NF:fcb.RxFinishFcbInitialization
title: RxFinishFcbInitialization function (fcb.h)
description: RxFinishFcbInitialization is used to finish initializing an FCB after the successful completion of a create operation by the network mini-redirector.
old-location: ifsk\rxfinishfcbinitialization.htm
tech.root: ifsk
ms.assetid: 290d0b06-ccf7-4792-b7bb-556092845e55
ms.date: 04/16/2018
ms.keywords: RDBSS_NTC_MAILSLOT, RDBSS_NTC_SPOOLFILE, RDBSS_NTC_STORAGE_TYPE_DIRECTORY, RDBSS_NTC_STORAGE_TYPE_FILE, RDBSS_NTC_STORAGE_TYPE_UNKNOWN, RxFinishFcbInitialization, RxFinishFcbInitialization function [Installable File System Drivers], fcb/RxFinishFcbInitialization, ifsk.rxfinishfcbinitialization, rxref_436f96f7-35ed-484b-8963-4afa559d3cfb.xml
ms.topic: function
f1_keywords:
 - "fcb/RxFinishFcbInitialization"
req.header: fcb.h
req.include-header: Mrxfcb.h, Nodetype.h, Fcb.h
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
req.lib: 
req.dll: 
req.irql: <= APC_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- fcb.h
api_name:
- RxFinishFcbInitialization
product:
- Windows
targetos: Windows
req.typenames: 
---

# RxFinishFcbInitialization function


## -description


<b>RxFinishFcbInitialization</b> is used to finish initializing an FCB after the successful completion of a create operation by the network mini-redirector. 


## -parameters




### -param Fcb

<p>A pointer to the MRX_FCB structure being initialized.</p>


### -param FileType

<p>The value indicating the storage type of entity that the FCB refers to. Possible options for this parameter include the following:</p>
  <table>
    <tr>
      <th>Value</th>
      <th>Meaning</th>
    </tr>
    <tr>
      <td width="40%">
        <a id="RDBSS_NTC_MAILSLOT"></a>
        <a id="rdbss_ntc_mailslot"></a>
        <dl>
          <dt>
            <b>RDBSS_NTC_MAILSLOT</b>
          </dt>
        </dl>
      </td>
      <td width="60%">
        <p>A mail slot.</p>
      </td>
    </tr>
    <tr>
      <td width="40%">
        <a id="RDBSS_NTC_SPOOLFILE"></a>
        <a id="rdbss_ntc_spoolfile"></a>
        <dl>
          <dt>
            <b>RDBSS_NTC_SPOOLFILE</b>
          </dt>
        </dl>
      </td>
      <td width="60%">
        <p>A printer spool file.</p>
      </td>
    </tr>
    <tr>
      <td width="40%">
        <a id="RDBSS_NTC_STORAGE_TYPE_DIRECTORY"></a>
        <a id="rdbss_ntc_storage_type_directory"></a>
        <dl>
          <dt>
            <b>RDBSS_NTC_STORAGE_TYPE_DIRECTORY</b>
          </dt>
        </dl>
      </td>
      <td width="60%">
        <p>A directory.</p>
      </td>
    </tr>
    <tr>
      <td width="40%">
        <a id="RDBSS_NTC_STORAGE_TYPE_UNKNOWN"></a>
        <a id="rdbss_ntc_storage_type_unknown"></a>
        <dl>
          <dt>
            <b>RDBSS_NTC_STORAGE_TYPE_UNKNOWN</b>
          </dt>
        </dl>
      </td>
      <td width="60%">
        <p>The storage type is unknown.</p>
      </td>
    </tr>
    <tr>
      <td width="40%">
        <a id="RDBSS_NTC_STORAGE_TYPE_FILE"></a>
        <a id="rdbss_ntc_storage_type_file"></a>
        <dl>
          <dt>
            <b>RDBSS_NTC_STORAGE_TYPE_FILE</b>
          </dt>
        </dl>
      </td>
      <td width="60%">
        <p>A file.</p>
      </td>
    </tr>
  </table>
  <p> </p>


### -param OPTIONAL

<p>Pointer to extra data that is required for initialization depending on the storage type of the FCB being initialized. This parameter may be a <b>NULL</b> pointer if no extra data is provided.</p>




## -returns



None




## -remarks



When called as a result of an IRP_MJ_CREATE, <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fcb/nf-fcb-rxcreatenetfcb">RxCreateNetFCB</a> is called first to create the FCB. If the <b>Type</b> member of the NET_ROOT to be created is not a NET_ROOT_MAILSLOT, then <b>RxFinishFcbInitialization</b> is called to finish the initialization of the FCB structure. 

If the <b>FcbState</b> member of the MRX_FCB structure pointed to by <i>MrxFcb</i> does not have the FCB_STATE_TIME_AND_SIZE_ALREADY_SET on, then the following members of the FCB will be updated from the <i>InitPacket</i> parameter if <i>InitPacket</i> is non <b>NULL</b>: <b>Attributes</b>, <b>NumberOfLinks</b>, <b>CreationTime</b>, <b>LastAccessTime</b>, <b>LastWriteTime</b>, <b>LastChangeTime</b>, <b>ActualAllocationLength</b>, <b>Header.AllocationSize</b>, <b>Header.FileSize</b>, and <b>Header.ValidDataLength</b>. The FCB_STATE_TIME_AND_SIZE_ALREADY_SET option is then set on in the <b>FcbState</b> member of the FCB structure.

If the storage type is an RDBSS_NTC_MAILSLOT and the FcbState member of the FCB does have the FCB_STATE_TIME_AND_SIZE_ALREADY_SET option set on, then the following members of the FCB structure for the mail slot will be initialized to 0: <b>Attributes</b>, <b>NumberOfLinks</b>,<b> CreationTime.QuadPart</b>,<b> LastAccessTime.QuadPart</b>, <b>LastWriteTime.QuadPart</b>, <b>LastChangeTime</b>.<b>QuadPart</b>, <b>ActualAllocationLength</b>, <b>Header.AllocationSize.QuadPart</b>, <b>Header.FileSize.QuadPart</b>, and <b>Header.ValidDataLength.QuadPart</b>




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fcb/nf-fcb-rxcreatenetfcb">RxCreateNetFCB</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fcb/nf-fcb-rxcreatenetfobx">RxCreateNetFobx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fcb/nf-fcb-rxcreatenetroot">RxCreateNetRoot</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fcb/nf-fcb-rxcreatesrvcall">RxCreateSrvCall</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fcb/nf-fcb-rxcreatesrvopen">RxCreateSrvOpen</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fcb/nf-fcb-rxcreatevnetroot">RxCreateVNetRoot</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/rxprocs/nf-rxprocs-rxdereference">RxDereference</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/rxprocs/nf-rxprocs-rxfinalizeconnection">RxFinalizeConnection</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/rxprocs/nf-rxprocs-rxfinalizenetfcb">RxFinalizeNetFcb</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fcb/nf-fcb-rxfinalizenetfobx">RxFinalizeNetFobx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fcb/nf-fcb-rxfinalizenetroot">RxFinalizeNetRoot</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fcb/nf-fcb-rxfinalizesrvcall">RxFinalizeSrvCall</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fcb/nf-fcb-rxfinalizesrvopen">RxFinalizeSrvOpen</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fcb/nf-fcb-rxfinalizevnetroot">RxFinalizeVNetRoot</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/rxprocs/nf-rxprocs-rxforcefinalizeallvnetroots">RxForceFinalizeAllVNetRoots</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/rxprocs/nf-rxprocs-rxreference">RxReference</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/rxprocs/nf-rxprocs-rxsetsrvcalldomainname">RxSetSrvCallDomainName</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fcb/nf-fcb-rxpdereferencenetfcb">RxpDereferenceNetFcb</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fcb/nf-fcb-rxpreferencenetfcb">RxpReferenceNetFcb</a>
 

 

