---
UID: NS:ntifs._FILE_NETWORK_PHYSICAL_NAME_INFORMATION
title: _FILE_NETWORK_PHYSICAL_NAME_INFORMATION (ntifs.h)
description: Contains the full UNC physical pathname for a file or directory on a remote file share.
old-location: ifsk\file_network_physical_name_information.htm
tech.root: ifsk
ms.assetid: 04F6A7B1-1198-4E5F-B6A8-70EEABE7CE83
ms.date: 04/16/2018
ms.keywords: "*PFILE_NETWORK_PHYSICAL_NAME_INFORMATION, FILE_NETWORK_PHYSICAL_NAME_INFORMATION, FILE_NETWORK_PHYSICAL_NAME_INFORMATION structure [Installable File System Drivers], PFILE_NETWORK_PHYSICAL_NAME_INFORMATION, PFILE_NETWORK_PHYSICAL_NAME_INFORMATION structure pointer [Installable File System Drivers], _FILE_NETWORK_PHYSICAL_NAME_INFORMATION, ifsk.file_network_physical_name_information, ntifs/FILE_NETWORK_PHYSICAL_NAME_INFORMATION, ntifs/PFILE_NETWORK_PHYSICAL_NAME_INFORMATION"
f1_keywords:
 - "ntifs/FILE_NETWORK_PHYSICAL_NAME_INFORMATION"
req.header: ntifs.h
req.include-header: Ntifs.h, Fltkernel.h
req.target-type: Windows
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
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- ntifs.h
api_name:
- FILE_NETWORK_PHYSICAL_NAME_INFORMATION
product:
- Windows
targetos: Windows
req.typenames: FILE_NETWORK_PHYSICAL_NAME_INFORMATION, *PFILE_NETWORK_PHYSICAL_NAME_INFORMATION
---

# _FILE_NETWORK_PHYSICAL_NAME_INFORMATION structure


## -description


Contains the full UNC physical pathname for a file or directory on a remote file share.


## -struct-fields




### -field FileNameLength

The length, in bytes, of the physical name in <b>FileName</b>.


### -field FileName

The full UNC path of the network file share of the target.


## -remarks



The <b>FILE_NETWORK_PHYSICAL_NAME_INFORMATION</b> structure is used to retrieve the network physical name information for a file. This operation can be performed in either of the following ways: 

<ul>
<li>
Call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ntqueryinformationfile">ZwQueryInformationFile</a>, passing <b>FileNetworkPhysicalNameInformation</b> as the value of <i>FileInformationClass</i> and passing a caller-allocated buffer formatted as a <b>FILE_NETWORK_PHYSICAL_NAME_INFORMATION</b> structure for the value of <i>FileInformation</i>. The <i>FileHandle</i> parameter specifies the file target for the name information.

<div class="alert"><b>Note</b>  File system minifilters must use <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltqueryinformationfile">FltQueryInformationFile</a> to query the physical name information.</div>
<div> </div>
</li>
<li>
Create an IRP with major function code <a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/irp-mj-query-information">IRP_MJ_QUERY_INFORMATION</a>. 

</li>
</ul>
The <b>FileName</b> of <b>FILE_NETWORK_PHYSICAL_NAME_INFORMATION</b> will contain the network name of the file target handle passed to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ntqueryinformationfile">ZwQueryInformationFile</a>. The physical network name returned is in the format of <i>\;X:\Server\ShareName\Dir1\Dir2\...\FileName</i>.

If the physical name is longer than the length set in <b>FileNameLength</b>, then STATUS_BUFFER_OVERFLOW is returned  from <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ntqueryinformationfile">ZwQueryInformationFile</a> and <b>FileNameLength</b> is updated with the number of bytes required to hold the entire name string. The count of characters in the name is <b>FileNameLength</b> / <b>sizeof</b>(WCHAR).

<div class="alert"><b>Note</b>  In the case where a file is cached on a client and its network physical name is queried, the path returned in <b>FileName</b> may not be known to the client cache.  The caching system may not associate the cached file with the file opened using the path returned in <b>FileName</b>.</div>
<div> </div>
The following is an example of querying the network physical name  information of a file target using <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ntqueryinformationfile">ZwQueryInformationFile</a>.

<div class="code"><span codelanguage="ManagedCPlusPlus"><table>
<tr>
<th>C++</th>
</tr>
<tr>
<td>
<pre>NTSTATUS GetPhysicalNetworkName(HANDLE Target, WCHAR *NetworkName, ULONG MaxNetworkNameLength)
{
    NTSTATUS Status;
    IO_STATUS_BLOCK IoStatus;
    ULONG NameInfoLength;
    PFILE_NETWORK_PHYSICAL_NAME_INFORMATION NetFileNameInfo = NULL;

    if ( MaxNetworkNameLength < sizeof(WCHAR) )
    {
        return STATUS_NAME_TOO_LONG;
    }
    if (NetworkName != NULL)
    {
        return STATUS_INVALID_PARAMETER;
    }

    NetworkName[0] = (WCHAR)0;	// initially terminate the output string;

    // set the initial name length, the one WCHAR in NetFileNameInfo.FileName is reserved for the terminatting NULL
    NameInfoLength = sizeof(PFILE_NETWORK_PHYSICAL_NAME_INFORMATION) +
                     min(1024, MaxNetworkNameLength - sizeof(WCHAR));
    NetFileNameInfo = (PFILE_NETWORK_PHYSICAL_NAME_INFORMATION)ExAllocatePool(PagedPool, NameInfoLength);

    if (NetFileNameInfo == NULL)
    {
        Status = STATUS_NO_MEMORY;
    }
    else
    {
        Status = ZwQueryInformationFile(Target,
                                        &IoStatus,
                                        NetFileNameInfo,
                                        NameInfoLength,
                                        FileNetworkPhysicalNameInformation);
    }
    if (Status == STATUS_BUFFER_OVERFLOW)
    {
        if (NetFileNameInfo->FileNameLength <= (MaxNetworkNameLength - sizeof(WCHAR)))
        {
            NameInfoLength += sizeof(PFILE_NETWORK_PHYSICAL_NAME_INFORMATION) + NetFileNameInfo->FileNameLength;
            ExFreePool(NetFileNameInfo);
            NetFileNameInfo = (PFILE_NETWORK_PHYSICAL_NAME_INFORMATION)ExAllocatePool(PagedPool, NameInfoLength);
            if (NetFileNameInfo == NULL)
            {
                Status = STATUS_NO_MEMORY;
            }
            else
            {
                Status = ZwQueryInformationFile(Target,
                                                &IoStatus,
                                                NetFileNameInfo,
                                                NameInfoLength,
                                                FileNetworkPhysicalNameInformation);
            }
        }
    }
    if (NetFileNameInfo != NULL)
    {
        if (NT_SUCCESS(Status))
        {
            NameInfoLength = min(NameInfoLength, NetFileNameInfo->FileNameLength);
            RtlCopyMemory(NetworkName, NetFileNameInfo->FileName, NameInfoLength);
            NetworkName[NameInfoLength / sizeof(WCHAR)] = (WCHAR)0;
        }
        ExFreePool(NetFileNameInfo);
    }

    return Status;
}
</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ne-wdm-_file_information_class">FILE_INFORMATION_CLASS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/irp-mj-query-information">IRP_MJ_QUERY_INFORMATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ntqueryinformationfile">ZwQueryInformationFile</a>
 

 

