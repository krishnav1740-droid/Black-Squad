<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<title>Salesforce CRM - New Case</title>

<style>
*{
    box-sizing:border-box;
}

body{
    margin:0;
    background:#f3f3f3;
    color:#181818;
    font-family:"Salesforce Sans",Arial,Helvetica,sans-serif;
}

/* ================= HEADER ================= */

.top-header{
    height:60px;
    background:#0b5cab;
    color:white;
    display:flex;
    align-items:center;
    padding:0 25px;
    box-shadow:0 2px 5px rgba(0,0,0,.25);
}

.logo{
    width:36px;
    height:36px;
    background:white;
    color:#0b5cab;
    border-radius:6px;
    display:flex;
    align-items:center;
    justify-content:center;
    font-size:21px;
    font-weight:bold;
    margin-right:12px;
}

.header-title{
    font-size:18px;
    font-weight:600;
}

.header-right{
    margin-left:auto;
    display:flex;
    gap:22px;
    font-size:13px;
}

/* ================= MAIN ================= */

.page{
    max-width:1250px;
    margin:20px auto;
    background:#fff;
    border:1px solid #d8dde6;
    border-radius:5px;
    box-shadow:0 2px 7px rgba(0,0,0,.12);
}

.page-header{
    position:relative;
    height:58px;
    display:flex;
    align-items:center;
    justify-content:center;
    border-bottom:1px solid #d8dde6;
    font-size:19px;
    font-weight:600;
}

.required-info{
    position:absolute;
    right:25px;
    font-size:12px;
    color:#666;
    font-weight:400;
}

.required{
    color:#ba0517;
    font-weight:bold;
}

/* ================= FORM ================= */

.form-body{
    padding:22px 28px 28px;
}

.section{
    margin-bottom:25px;
}

.section-title{
    background:#f3f3f3;
    border:1px solid #d8dde6;
    border-radius:3px;
    padding:10px 13px;
    margin-bottom:15px;
    font-size:14px;
    font-weight:700;
    color:#181818;
}

.section-title.blue{
    background:#eef4ff;
    color:#032d60;
    border-left:4px solid #0176d3;
}

.form-grid{
    display:grid;
    grid-template-columns:1fr 1fr;
    gap:18px 30px;
}

.field{
    min-width:0;
}

label{
    display:block;
    margin-bottom:6px;
    font-size:13px;
}

input,
select,
textarea{
    width:100%;
    min-height:38px;
    padding:8px 11px;
    border:1px solid #747474;
    border-radius:4px;
    background:#fff;
    color:#181818;
    font-family:inherit;
    font-size:13px;
    outline:none;
}

input:focus,
select:focus,
textarea:focus{
    border:2px solid #0176d3;
    box-shadow:0 0 3px rgba(1,118,211,.25);
}

input[readonly]{
    background:#f8f8f8;
}

/* AUTO LOCKED */

select.auto-locked{
    background:#f3f3f3;
    color:#181818;
    font-weight:600;
    border-color:#b0b0b0;
    cursor:not-allowed;
}

.auto-indicator{
    display:none;
    margin-top:4px;
    font-size:10px;
    color:#0176d3;
}

.auto-indicator.show{
    display:block;
}

/* Search fields */

.search-box{
    position:relative;
}

.search-box input{
    padding-right:40px;
}

.search-icon{
    position:absolute;
    right:12px;
    top:9px;
    font-size:19px;
    color:#444;
}

/* ================= BUTTONS ================= */

.actions{
    display:flex;
    justify-content:flex-end;
    gap:10px;
    padding-top:18px;
    border-top:1px solid #ddd;
}

button{
    min-height:38px;
    padding:0 20px;
    border-radius:4px;
    border:1px solid #747474;
    background:#fff;
    font-family:inherit;
    font-size:13px;
    cursor:pointer;
}

.btn-primary{
    background:#0176d3;
    border-color:#0176d3;
    color:white;
    font-weight:600;
}

.btn-primary:hover{
    background:#014486;
}

.btn-cancel:hover{
    background:#f3f3f3;
}

/* ================= LAST ACTION ================= */

.last-action{
    max-width:1250px;
    margin:20px auto 40px;
    background:white;
    border:1px solid #d8dde6;
    border-radius:5px;
    box-shadow:0 2px 5px rgba(0,0,0,.08);
}

.last-action-header{
    padding:14px 17px;
    background:#f3f3f3;
    border-bottom:1px solid #d8dde6;
    font-size:15px;
    font-weight:700;
    color:#032d60;
}

.ticket-table{
    width:100%;
    border-collapse:collapse;
}

.ticket-table th{
    padding:11px;
    background:#fafaf9;
    border-bottom:1px solid #ddd;
    text-align:left;
    font-size:12px;
    color:#444;
}

.ticket-table td{
    padding:11px;
    border-bottom:1px solid #eee;
    font-size:12px;
    vertical-align:top;
}

.ticket-number{
    color:#0176d3;
    font-weight:700;
    cursor:pointer;
}

.ticket-number:hover{
    text-decoration:underline;
}

.status{
    display:inline-block;
    padding:4px 9px;
    border-radius:12px;
    font-size:10px;
    font-weight:700;
}

.status-pending{
    background:#ecebea;
    color:#444;
}

.status-open{
    background:#e5f3ff;
    color:#032d60;
}

.status-auto{
    background:#fff1d6;
    color:#8a4b00;
}

.status-closed{
    background:#e5f6ed;
    color:#2e844a;
}

.empty{
    text-align:center;
    padding:28px;
    color:#666;
    font-size:13px;
}

/* ================= MODAL ================= */

.modal-overlay{
    position:fixed;
    inset:0;
    z-index:1000;
    display:none;
    align-items:center;
    justify-content:center;
    padding:20px;
    background:rgba(0,0,0,.45);
}

.modal-overlay.show{
    display:flex;
}

.modal{
    width:min(900px,96vw);
    max-height:92vh;
    overflow:auto;
    background:white;
    border-radius:5px;
    box-shadow:0 10px 35px rgba(0,0,0,.35);
    animation:openModal .18s ease-out;
}

@keyframes openModal{
    from{
        opacity:0;
        transform:translateY(-12px);
    }
    to{
        opacity:1;
        transform:translateY(0);
    }
}

.modal-header{
    min-height:70px;
    position:relative;
    display:flex;
    align-items:center;
    justify-content:center;
    border-bottom:1px solid #d8dde6;
}

.modal-header h2{
    margin:0;
    font-size:23px;
    font-weight:400;
}

.close-x{
    position:absolute;
    right:14px;
    top:14px;
    width:38px;
    height:38px;
    border:0;
    background:transparent;
    font-size:28px;
    padding:0;
    color:#444;
}

.close-x:hover{
    background:#eee;
    border-radius:50%;
}

.modal-body{
    padding:28px 35px;
}

.modal-grid{
    display:grid;
    grid-template-columns:1fr 1fr;
    gap:25px;
}

.modal-footer{
    display:flex;
    justify-content:flex-end;
    gap:10px;
    padding:15px 30px;
    background:#fafaf9;
    border-top:1px solid #ddd;
}

/* ================= LAST ACTION POPUP ================= */

.sub-category-info{
    background:#f3f8fc;
    border-left:4px solid #0176d3;
    padding:13px;
    margin-bottom:22px;
    font-size:12px;
    line-height:1.6;
}

.description-field{
    margin-top:22px;
}

.description-field textarea{
    min-height:105px;
}

/* ================= CLOSE CASE ================= */

.desk-info{
    background:#f3f3f3;
    border:1px solid #ddd;
    border-radius:4px;
    margin-bottom:25px;
    padding:12px 15px;
}

.desk-row{
    display:grid;
    grid-template-columns:180px 1fr;
    gap:15px;
    padding:6px 0;
    font-size:13px;
}

.desk-label{
    color:#666;
    font-weight:600;
}

/* ================= TOAST ================= */

.toast{
    position:fixed;
    right:25px;
    bottom:25px;
    z-index:2000;
    display:none;
    background:#2e844a;
    color:white;
    padding:14px 20px;
    border-radius:4px;
    box-shadow:0 4px 15px rgba(0,0,0,.25);
    font-size:13px;
}

.toast.show{
    display:block;
}

/* ================= RESPONSIVE ================= */

@media(max-width:800px){

    .form-grid,
    .modal-grid{
        grid-template-columns:1fr;
    }

    .required-info{
        display:none;
    }

    .page{
        margin:10px;
    }

    .form-body{
        padding:15px;
    }

    .last-action{
        margin:10px;
        overflow-x:auto;
    }

    .ticket-table{
        min-width:900px;
    }

    .modal-body{
        padding:22px;
    }

    .header-right{
        display:none;
    }

    .top-header{
        padding:0 12px;
    }
}
</style>
</head>

<body>

<!-- =====================================================
     HEADER
===================================================== -->

<div class="top-header">

    <div class="logo">☁</div>

    <div class="header-title">
        Salesforce CRM
    </div>

    <div class="header-right">
        <span>Search</span>
        <span>Help</span>
        <span>Notifications</span>
        <span>User</span>
    </div>

</div>


<!-- =====================================================
     NEW CASE
===================================================== -->

<div class="page">

    <div class="page-header">

        New Case: Default

        <span class="required-info">
            <span class="required">*</span>
            = Required Information
        </span>

    </div>


    <div class="form-body">


        <!-- ================= CALLING INFORMATION ================= -->

        <div class="section">

            <div class="section-title blue">
                Calling Information
            </div>

            <div class="form-grid">

                <div class="field">

                    <label>
                        <span class="required">*</span>
                        Calling Mobile Number
                    </label>

                    <input
                        type="text"
                        id="callingMobile"
                        placeholder="Waiting for CTI..."
                        oninput="mobileChanged()"
                    >

                </div>


                <div class="field">

                    <label>
                        <span class="required">*</span>
                        Intimator / Caller Contact Number
                    </label>

                    <input
                        type="text"
                        id="callerContact"
                        readonly
                    >

                </div>

            </div>

        </div>


        <!-- ================= CUSTOMER ================= -->

        <div class="section">

            <div class="section-title">
                Search by Customer Name or Mobile Number Or Policy
            </div>

            <div class="form-grid">


                <div class="field">

                    <label>
                        <span class="required">*</span>
                        Customer Name
                    </label>

                    <div class="search-box">

                        <input
                            type="text"
                            id="customerName"
                            placeholder="Search Customers..."
                        >

                        <span class="search-icon">
                            ⌕
                        </span>

                    </div>

                </div>


                <div class="field">

                    <label>
                        <span class="required">*</span>
                        Insurance Policy
                    </label>

                    <div class="search-box">

                        <input
                            type="text"
                            id="insurancePolicy"
                            placeholder="Search Insurance Policies..."
                        >

                        <span class="search-icon">
                            ⌕
                        </span>

                    </div>

                </div>


                <div class="field">

                    <label>
                        Intimator / Caller Name
                    </label>

                    <input
                        type="text"
                        id="callerName"
                    >

                </div>


                <div class="field">

                    <label>
                        <span class="required">*</span>
                        Insured Member
                    </label>

                    <div class="search-box">

                        <input
                            type="text"
                            id="insuredMember"
                            placeholder="Search Members..."
                        >

                        <span class="search-icon">
                            ⌕
                        </span>

                    </div>

                </div>


                <div class="field">

                    <label>
                        <span class="required">*</span>
                        Language
                    </label>

                    <select id="language">

                        <option value="">
                            --None--
                        </option>

                        <option value="English">
                            English
                        </option>

                        <option value="Tamil">
                            Tamil
                        </option>

                        <option value="Telugu">
                            Telugu
                        </option>

                        <option value="Hindi">
                            Hindi
                        </option>

                        <option value="Malayalam">
                            Malayalam
                        </option>

                        <option value="Kannada">
                            Kannada
                        </option>

                    </select>

                </div>

            </div>

        </div>


        <!-- ================= CASE DETAILS ================= -->

        <div class="section">

            <div class="section-title">
                Case Details
            </div>


            <div class="form-grid">


                <!-- REASON -->

                <div class="field">

                    <label>
                        <span class="required">*</span>
                        Reason for Calling
                    </label>

                    <select id="reasonForCalling">

                        <option value="">
                            --None--
                        </option>

                        <option value="TELE CONSULTATION">
                            TELE CONSULTATION
                        </option>

                        <option value="HOME HEALTH CARE">
                            HOME HEALTH CARE
                        </option>

                        <option value="SPECIALIST OPINION">
                            SPECIALIST OPINION
                        </option>

                        <option value="HOSPITALIZATION ENQUIRY">
                            HOSPITALIZATION ENQUIRY
                        </option>

                        <option value="NON PRATHAM POLICY RELATED">
                            NON PRATHAM POLICY RELATED
                        </option>

                        <option value="NON PRATHAM CLAIM RELATED">
                            NON PRATHAM CLAIM RELATED
                        </option>

                        <option value="OTHERS">
                            OTHERS
                        </option>

                    </select>

                    <div
                        id="reasonAuto"
                        class="auto-indicator"
                    >
                        🔒 Auto fetched from Case Source
                    </div>

                </div>


                <!-- PRIORITY -->

                <div class="field">

                    <label>
                        <span class="required">*</span>
                        Priority Flag
                    </label>

                    <select id="priority">

                        <option value="LOW">
                            LOW
                        </option>

                        <option value="MEDIUM">
                            MEDIUM
                        </option>

                        <option value="HIGH">
                            HIGH
                        </option>

                    </select>

                </div>


                <!-- CASE TYPE -->

                <div class="field">

                    <label>
                        <span class="required">*</span>
                        Case Type
                    </label>

                    <select id="caseType">

                        <option value="">
                            --None--
                        </option>

                        <option value="TTS PRATHAM">
                            TTS PRATHAM
                        </option>

                        <option value="TTS HHC">
                            TTS HHC
                        </option>

                    </select>

                    <div
                        id="caseTypeAuto"
                        class="auto-indicator"
                    >
                        🔒 Auto fetched from Case Source
                    </div>

                </div>


                <!-- CASE SOURCE -->

                <div class="field">

                    <label>
                        <span class="required">*</span>
                        Case Source
                    </label>

                    <select
                        id="caseSource"
                        onchange="caseSourceChanged()"
                    >

                        <option value="">
                            --None--
                        </option>

                        <option value="INBOUND HELPLINE">
                            INBOUND HELPLINE
                        </option>

                        <option value="INBOUND EMAIL (INTIMATION REQUEST)">
                            INBOUND EMAIL (INTIMATION REQUEST)
                        </option>

                        <option value="INBOUND - GENERAL LINE (INTIMATION REQUEST)">
                            INBOUND - GENERAL LINE (INTIMATION REQUEST)
                        </option>

                        <option value="INBOUND - GENERAL LINE (PRODUCT ENQUIRY)">
                            INBOUND - GENERAL LINE (PRODUCT ENQUIRY)
                        </option>

                        <option value="INBOUND - GENERAL LINE (DISEASE COVERAGE)">
                            INBOUND - GENERAL LINE (DISEASE COVERAGE)
                        </option>

                        <option value="STAR ATOM">
                            STAR ATOM
                        </option>

                        <option value="STAR APP INTIMATION">
                            STAR APP INTIMATION
                        </option>

                        <option value="TREATMENT CALCULATOR">
                            TREATMENT CALCULATOR
                        </option>

                        <option value="INBOUND HELPLINE PRATHAM">
                            INBOUND HELPLINE PRATHAM
                        </option>

                        <option value="INBOUND HELPLINE HHC">
                            INBOUND HELPLINE HHC
                        </option>

                    </select>

                </div>


                <!-- SPECIALITY -->

                <div class="field">

                    <label>
                        Speciality
                    </label>

                    <select id="speciality">

                        <option value="">
                            --None--
                        </option>

                        <option>GENERAL MEDICINE</option>
                        <option>GENERAL SURGERY</option>
                        <option>CARDIOLOGY</option>
                        <option>NEUROLOGY</option>
                        <option>ORTHOPAEDICS</option>
                        <option>PAEDIATRICS</option>
                        <option>GYNAECOLOGY</option>
                        <option>OBSTETRICS</option>
                        <option>DERMATOLOGY</option>
                        <option>ENT</option>
                        <option>OPHTHALMOLOGY</option>
                        <option>PULMONOLOGY</option>
                        <option>NEPHROLOGY</option>
                        <option>UROLOGY</option>
                        <option>GASTROENTEROLOGY</option>
                        <option>ONCOLOGY</option>
                        <option>ENDOCRINOLOGY</option>
                        <option>PSYCHIATRY</option>
                        <option>DENTISTRY</option>
                        <option>RHEUMATOLOGY</option>

                    </select>

                </div>

            </div>

        </div>


        <!-- ================= ALTERNATE CONTACT ================= -->

        <div class="section">

            <div class="section-title">
                Capture Alternate Contact Details
            </div>

            <div class="form-grid">

                <div class="field">

                    <label>
                        Alternate Mobile Number
                    </label>

                    <input
                        type="text"
                        id="alternateMobile"
                    >

                </div>


                <div class="field">

                    <label>
                        Alternate Email Id
                    </label>

                    <input
                        type="email"
                        id="alternateEmail"
                    >

                </div>

            </div>

        </div>


        <!-- ================= BUTTONS ================= -->

        <div class="actions">

            <button
                class="btn-cancel"
                onclick="resetForm()"
            >
                Cancel
            </button>

            <button
                class="btn-cancel"
                onclick="saveAndNew()"
            >
                Save & New
            </button>

            <button
                class="btn-primary"
                onclick="createTicket()"
            >
                Save
            </button>

        </div>

    </div>

</div>


<!-- =====================================================
     LAST ACTION WITH TICKET NUMBER
===================================================== -->

<div class="last-action">

    <div class="last-action-header">
        LAST ACTION WITH TICKET NUMBER
    </div>

    <div id="ticketContainer">

        <div class="empty">
            No ticket created yet.
        </div>

    </div>

</div>


<!-- =====================================================
     LAST ACTION POPUP
===================================================== -->

<div
    class="modal-overlay"
    id="subCategoryModal"
>

    <div class="modal">


        <div class="modal-header">

            <h2>
                Last Action
            </h2>

            <button
                class="close-x"
                onclick="closeSubCategoryModal()"
            >
                ×
            </button>

        </div>


        <div class="modal-body">


            <div class="sub-category-info">

                <strong id="selectedTicketTitle">
                    Ticket
                </strong>

                <br>

                Select the Last Action Sub Category and
                enter the description for this ticket.

            </div>


            <div class="modal-grid">


                <div class="field">

                    <label>
                        <span class="required">*</span>
                        Sub Category
                    </label>

                    <select id="subCategory">

                        <option value="">
                            --None--
                        </option>

                        <optgroup label="OPEN">

                            <option value="Caller Will Confirm With Family / Hospital">
                                Caller Will Confirm With Family / Hospital
                            </option>

                            <option value="Intimation Registered">
                                Intimation Registered
                            </option>

                            <option value="Pratham Not Interested">
                                Pratham Not Interested
                            </option>

                            <option value="Call Back">
                                Call Back
                            </option>

                        </optgroup>


                        <optgroup label="AUTO CLOSE">

                            <option value="Unanswered">
                                Unanswered
                            </option>

                            <option value="NOT PLANNING FOR ADMISSION">
                                NOT PLANNING FOR ADMISSION
                            </option>

                            <option value="CLAIM REGISTERED / ALREADY ADMITTED">
                                CLAIM REGISTERED / ALREADY ADMITTED
                            </option>

                            <option value="NOT ELIGIBLE TO CALL / CLAIM">
                                NOT ELIGIBLE TO CALL / CLAIM
                            </option>

                            <option value="DISCONNECTED DURING CONVERSATION">
                                DISCONNECTED DURING CONVERSATION
                            </option>

                            <option value="NON PRATHAM CALL">
                                NON PRATHAM CALL
                            </option>

                            <option value="VOICE ISSUE">
                                VOICE ISSUE
                            </option>

                        </optgroup>

                    </select>

                </div>


                <div class="field">

                    <label>
                        Ticket Number
                    </label>

                    <input
                        type="text"
                        id="popupTicketNumber"
                        readonly
                    >

                </div>

            </div>


            <div class="field description-field">

                <label>
                    <span class="required">*</span>
                    Description
                </label>

                <textarea
                    id="subCategoryDescription"
                    placeholder="Enter description..."
                ></textarea>

            </div>

        </div>


        <div class="modal-footer">

            <button
                class="btn-cancel"
                onclick="closeSubCategoryModal()"
            >
                Cancel
            </button>

            <button
                class="btn-primary"
                onclick="saveLastAction()"
            >
                Save
            </button>

        </div>

    </div>

</div>


<!-- =====================================================
     CLOSE CASE POPUP
===================================================== -->

<div
    class="modal-overlay"
    id="closeCaseModal"
>

    <div class="modal">


        <div class="modal-header">

            <h2>
                Close Case
            </h2>

            <button
                class="close-x"
                onclick="closeCloseCaseModal()"
            >
                ×
            </button>

        </div>


        <div class="modal-body">


            <div class="desk-info">

                <div class="desk-row">

                    <div class="desk-label">
                        Ticket Number
                    </div>

                    <div id="deskTicketNumber">
                    </div>

                </div>


                <div class="desk-row">

                    <div class="desk-label">
                        Sub Category
                    </div>

                    <div id="deskSubCategory">
                    </div>

                </div>

            </div>


            <div class="modal-grid">


                <div class="field">

                    <label>
                        <span class="required">*</span>
                        Ticket Closure Reason
                    </label>

                    <select id="closedRemarks">

                        <option value="">
                            --None--
                        </option>

                        <option value="Intimation registered Pratham">
                            Intimation registered Pratham
                        </option>

                        <option value="Intimation Registered">
                            Intimation Registered
                        </option>

                        <option value="Bad Past Experience with the Hospital">
                            Bad Past Experience with the Hospital
                        </option>

                        <option value="Claim already processed before call (No O/B call)">
                            Claim already processed before call (No O/B call)
                        </option>

                        <option value="Hospital Too far">
                            Hospital Too far
                        </option>

                        <option value="Unavailability of Pratham">
                            Unavailability of Pratham
                        </option>

                        <option value="Unavailability of Speciality">
                            Unavailability of Speciality
                        </option>

                        <option value="Lower Cost in Existing Hospital">
                            Lower Cost in Existing Hospital
                        </option>

                        <option value="Not Eligible for Claim">
                            Not Eligible for Claim
                        </option>

                        <option value="Pratham Not Reachable">
                            Pratham Not Reachable
                        </option>

                    </select>

                </div>


                <div class="field">

                    <label>
                        Comments
                    </label>

                    <textarea
                        id="closureDescription"
                        placeholder="Enter comments..."
                    ></textarea>

                </div>

            </div>

        </div>


        <div class="modal-footer">

            <button
                class="btn-cancel"
                onclick="closeCloseCaseModal()"
            >
                Cancel
            </button>

            <button
                class="btn-primary"
                onclick="closeTicket()"
            >
                Save
            </button>

        </div>

    </div>

</div>


<!-- =====================================================
     TOAST
===================================================== -->

<div
    class="toast"
    id="toast"
></div>


<script>

/* =====================================================
   TICKET STORAGE
===================================================== */

let tickets =
    JSON.parse(localStorage.getItem("crmTickets")) || [];

let selectedTicketIndex = null;


/* =====================================================
   CASE SOURCE AUTO FETCH MAPPING
===================================================== */

const caseSourceMapping = {

    "INBOUND HELPLINE PRATHAM": {
        reason: "HOSPITALIZATION ENQUIRY",
        caseType: "TTS PRATHAM"
    },

    "INBOUND HELPLINE HHC": {
        reason: "HOME HEALTH CARE",
        caseType: "TTS HHC"
    },

    "INBOUND EMAIL (INTIMATION REQUEST)": {
        reason: "HOSPITALIZATION ENQUIRY",
        caseType: "TTS PRATHAM"
    },

    "INBOUND - GENERAL LINE (INTIMATION REQUEST)": {
        reason: "HOSPITALIZATION ENQUIRY",
        caseType: "TTS PRATHAM"
    },

    "INBOUND - GENERAL LINE (PRODUCT ENQUIRY)": {
        reason: "HOSPITALIZATION ENQUIRY",
        caseType: "TTS PRATHAM"
    },

    "INBOUND - GENERAL LINE (DISEASE COVERAGE)": {
        reason: "HOSPITALIZATION ENQUIRY",
        caseType: "TTS PRATHAM"
    },

    "STAR ATOM": {
        reason: "HOSPITALIZATION ENQUIRY",
        caseType: "TTS PRATHAM"
    },

    "STAR APP INTIMATION": {
        reason: "HOSPITALIZATION ENQUIRY",
        caseType: "TTS PRATHAM"
    },

    "TREATMENT CALCULATOR": {
        reason: "HOSPITALIZATION ENQUIRY",
        caseType: "TTS PRATHAM"
    }

};


/* =====================================================
   CASE SOURCE CHANGE
===================================================== */

function caseSourceChanged(){

    const source =
        document.getElementById("caseSource").value.trim();

    const reason =
        document.getElementById("reasonForCalling");

    const caseType =
        document.getElementById("caseType");

    const reasonAuto =
        document.getElementById("reasonAuto");

    const caseTypeAuto =
        document.getElementById("caseTypeAuto");


    /*
       ALWAYS CLEAR OLD AUTO VALUES
       BEFORE APPLYING NEW VALUE
    */

    reason.value = "";
    caseType.value = "";

    reason.classList.remove("auto-locked");
    caseType.classList.remove("auto-locked");

    reasonAuto.classList.remove("show");
    caseTypeAuto.classList.remove("show");


    /*
       INBOUND HELPLINE
       = MANUAL
    */

    if(source === "INBOUND HELPLINE"){

        reason.disabled = false;
        caseType.disabled = false;

        return;
    }


    /*
       NO CASE SOURCE
    */

    if(source === ""){

        reason.disabled = false;
        caseType.disabled = false;

        return;
    }


    /*
       AUTO FETCH
    */

    const mapping =
        caseSourceMapping[source];


    if(mapping){

        reason.value =
            mapping.reason;

        caseType.value =
            mapping.caseType;


        /*
           LOCK AUTO FETCHED FIELDS
        */

        reason.disabled = true;
        caseType.disabled = true;


        reason.classList.add("auto-locked");
        caseType.classList.add("auto-locked");


        reasonAuto.classList.add("show");
        caseTypeAuto.classList.add("show");


        console.log(
            "CASE SOURCE:",
            source
        );

        console.log(
            "AUTO REASON:",
            mapping.reason
        );

        console.log(
            "AUTO CASE TYPE:",
            mapping.caseType
        );

    }

}


/* =====================================================
   MOBILE NUMBER
===================================================== */

function mobileChanged(){

    const mobile =
        document.getElementById(
            "callingMobile"
        ).value;

    document.getElementById(
        "callerContact"
    ).value = mobile;

}


/* =====================================================
   CREATE TICKET
===================================================== */

function createTicket(){

    const source =
        document.getElementById(
            "caseSource"
        ).value.trim();


    const reason =
        document.getElementById(
            "reasonForCalling"
        ).value;


    const caseType =
        document.getElementById(
            "caseType"
        ).value;


    /* REQUIRED VALIDATION */

    if(!document.getElementById("callingMobile").value.trim()){

        alert("Please enter Calling Mobile Number.");
        return;

    }


    if(!source){

        alert("Please select Case Source.");
        return;

    }


    if(!reason){

        alert("Please select Reason for Calling.");
        return;

    }


    if(!caseType){

        alert("Please select Case Type.");
        return;

    }


    /* TICKET NUMBER */

    const ticketNumber =
        "TKT-" +
        Date.now();


    /* CREATE OBJECT */

    const ticket = {

        ticketNumber:

            ticketNumber,

        callingMobile:

            document.getElementById(
                "callingMobile"
            ).value,

        callerContact:

            document.getElementById(
                "callerContact"
            ).value,

        customerName:

            document.getElementById(
                "customerName"
            ).value,

        insurancePolicy:

            document.getElementById(
                "insurancePolicy"
            ).value,

        callerName:

            document.getElementById(
                "callerName"
            ).value,

        insuredMember:

            document.getElementById(
                "insuredMember"
            ).value,

        language:

            document.getElementById(
                "language"
            ).value,

        caseSource:

            source,

        reasonForCalling:

            reason,

        priority:

            document.getElementById(
                "priority"
            ).value,

        caseType:

            caseType,

        speciality:

            document.getElementById(
                "speciality"
            ).value,

        alternateMobile:

            document.getElementById(
                "alternateMobile"
            ).value,

        alternateEmail:

            document.getElementById(
                "alternateEmail"
            ).value,

        subCategory: "",

        subCategoryDescription: "",

        closedRemarks: "",

        closureDescription: "",

        status:
            "PENDING SUB CATEGORY",

        createdAt:
            new Date().toLocaleString(),

        closedAt: ""

    };


    /*
       ADD NEW TICKET
    */

    tickets.unshift(ticket);

    saveTickets();

    renderTickets();


    showToast(
        "Case created successfully - " +
        ticketNumber
    );


    /*
       OPEN LAST ACTION POPUP
    */

    selectedTicketIndex = 0;

    openSubCategoryModal(0);

}


/* =====================================================
   LAST ACTION POPUP
===================================================== */

function openSubCategoryModal(index){

    selectedTicketIndex = index;

    const ticket =
        tickets[index];


    document.getElementById(
        "selectedTicketTitle"
    ).textContent =
        "Ticket " +
        ticket.ticketNumber;


    document.getElementById(
        "popupTicketNumber"
    ).value =
        ticket.ticketNumber;


    document.getElementById(
        "subCategory"
    ).value =
        ticket.subCategory || "";


    document.getElementById(
        "subCategoryDescription"
    ).value =
        ticket.subCategoryDescription || "";


    document.getElementById(
        "subCategoryModal"
    ).classList.add("show");

}


/* =====================================================
   SAVE LAST ACTION
===================================================== */

function saveLastAction(){

    if(selectedTicketIndex === null)
        return;


    const ticket =
        tickets[selectedTicketIndex];


    const subCategory =
        document.getElementById(
            "subCategory"
        ).value;


    const description =
        document.getElementById(
            "subCategoryDescription"
        ).value.trim();


    if(!subCategory){

        alert(
            "Please select Sub Category."
        );

        return;

    }


    if(!description){

        alert(
            "Please enter Description."
        );

        return;

    }


    ticket.subCategory =
        subCategory;


    ticket.subCategoryDescription =
        description;


    /* AUTO CLOSE LIST */

    const autoCloseOptions = [

        "Unanswered",

        "NOT PLANNING FOR ADMISSION",

        "CLAIM REGISTERED / ALREADY ADMITTED",

        "NOT ELIGIBLE TO CALL / CLAIM",

        "DISCONNECTED DURING CONVERSATION",

        "NON PRATHAM CALL",

        "VOICE ISSUE"

    ];


    /*
       AUTO CLOSE
    */

    if(
        autoCloseOptions.includes(
            subCategory
        )
    ){

        ticket.status =
            "AUTO CLOSE";


        saveTickets();

        renderTickets();

        closeSubCategoryModal();


        showToast(
            ticket.ticketNumber +
            " - AUTO CLOSE"
        );


        selectedTicketIndex = null;

        return;

    }


    /*
       OPEN
    */

    ticket.status =
        "OPEN";


    saveTickets();

    renderTickets();

    closeSubCategoryModal();


    showToast(
        ticket.ticketNumber +
        " - OPEN"
    );

}


/* =====================================================
   OPEN TICKET / DESK
===================================================== */

function openDesk(index){

    const ticket =
        tickets[index];


    if(ticket.status !== "OPEN")
        return;


    selectedTicketIndex =
        index;


    document.getElementById(
        "deskTicketNumber"
    ).textContent =
        ticket.ticketNumber;


    document.getElementById(
        "deskSubCategory"
    ).textContent =
        ticket.subCategory;


    document.getElementById(
        "closedRemarks"
    ).value =
        ticket.closedRemarks || "";


    document.getElementById(
        "closureDescription"
    ).value =
        ticket.closureDescription || "";


    document.getElementById(
        "closeCaseModal"
    ).classList.add("show");

}


/* =====================================================
   CLOSE CASE
===================================================== */

function closeTicket(){

    if(selectedTicketIndex === null)
        return;


    const ticket =
        tickets[selectedTicketIndex];


    const remarks =
        document.getElementById(
            "closedRemarks"
        ).value;


    const description =
        document.getElementById(
            "closureDescription"
        ).value.trim();


    if(!remarks){

        alert(
            "Please select Ticket Closure Reason."
        );

        return;

    }


    if(!description){

        alert(
            "Please enter Comments / Description."
        );

        return;

    }


    ticket.closedRemarks =
        remarks;


    ticket.closureDescription =
        description;


    ticket.status =
        "CLOSED";


    ticket.closedAt =
        new Date().toLocaleString();


    saveTickets();

    renderTickets();

    closeCloseCaseModal();


    showToast(
        ticket.ticketNumber +
        " - CLOSED"
    );


    selectedTicketIndex = null;

}


/* =====================================================
   RENDER LAST ACTION TABLE
===================================================== */

function renderTickets(){

    const container =
        document.getElementById(
            "ticketContainer"
        );


    if(tickets.length === 0){

        container.innerHTML = `
            <div class="empty">
                No ticket created yet.
            </div>
        `;

        return;

    }


    let html = `

        <table class="ticket-table">

            <thead>

                <tr>

                    <th>
                        Ticket Number
                    </th>

                    <th>
                        Case Source
                    </th>

                    <th>
                        Last Action
                    </th>

                    <th>
                        Description
                    </th>

                    <th>
                        Status
                    </th>

                    <th>
                        Created Time
                    </th>

                </tr>

            </thead>

            <tbody>

    `;


    tickets.forEach(
        (ticket,index)=>{


        let statusClass =
            "status-pending";


        if(
            ticket.status === "OPEN"
        ){

            statusClass =
                "status-open";

        }


        if(
            ticket.status === "AUTO CLOSE"
        ){

            statusClass =
                "status-auto";

        }


        if(
            ticket.status === "CLOSED"
        ){

            statusClass =
                "status-closed";

        }


        let clickAction = "";


        if(
            ticket.status ===
            "PENDING SUB CATEGORY"
        ){

            clickAction =
                `onclick="openSubCategoryModal(${index})"`;

        }


        else if(
            ticket.status === "OPEN"
        ){

            clickAction =
                `onclick="openDesk(${index})"`;

        }


        let description =
            ticket.subCategoryDescription
            || "-";


        if(
            ticket.status === "CLOSED"
        ){

            description +=
                "<br><br><strong>Closure:</strong> " +
                escapeHTML(
                    ticket.closureDescription
                );

        }


        html += `

            <tr>

                <td>

                    <span
                        class="ticket-number"
                        ${clickAction}
                    >
                        ${escapeHTML(
                            ticket.ticketNumber
                        )}
                    </span>

                </td>


                <td>
                    ${escapeHTML(
                        ticket.caseSource
                    )}
                </td>


                <td>

                    ${
                        ticket.subCategory

                        ? escapeHTML(
                            ticket.subCategory
                          )

                        : `
                            <span
                                style="color:#888"
                            >
                                Select Last Action
                            </span>
                          `
                    }

                </td>


                <td>
                    ${description}
                </td>


                <td>

                    <span
                        class="status ${statusClass}"
                    >

                        ${escapeHTML(
                            ticket.status
                        )}

                    </span>

                </td>


                <td>
                    ${escapeHTML(
                        ticket.createdAt
                    )}
                </td>

            </tr>

        `;

    });


    html += `

            </tbody>

        </table>

    `;


    container.innerHTML =
        html;

}


/* =====================================================
   RESET FORM
===================================================== */

function resetForm(){

    document.querySelectorAll(
        ".form-body input"
    ).forEach(
        input => {

            input.value = "";

        }
    );


    document.querySelectorAll(
        ".form-body select"
    ).forEach(
        select => {

            select.selectedIndex = 0;

        }
    );


    document.getElementById(
        "reasonForCalling"
    ).disabled = false;


    document.getElementById(
        "caseType"
    ).disabled = false;


    document.getElementById(
        "reasonForCalling"
    ).classList.remove(
        "auto-locked"
    );


    document.getElementById(
        "caseType"
    ).classList.remove(
        "auto-locked"
    );


    document.getElementById(
        "reasonAuto"
    ).classList.remove(
        "show"
    );


    document.getElementById(
        "caseTypeAuto"
    ).classList.remove(
        "show"
    );

}


/* =====================================================
   SAVE & NEW
===================================================== */

function saveAndNew(){

    createTicket();

}


/* =====================================================
   LOCAL STORAGE
===================================================== */

function saveTickets(){

    localStorage.setItem(
        "crmTickets",
        JSON.stringify(tickets)
    );

}


/* =====================================================
   CLOSE POPUPS
===================================================== */

function closeSubCategoryModal(){

    document.getElementById(
        "subCategoryModal"
    ).classList.remove(
        "show"
    );

}


function closeCloseCaseModal(){

    document.getElementById(
        "closeCaseModal"
    ).classList.remove(
        "show"
    );

}


/* =====================================================
   TOAST
===================================================== */

function showToast(message){

    const toast =
        document.getElementById(
            "toast"
        );


    toast.textContent =
        message;


    toast.classList.add(
        "show"
    );


    setTimeout(
        () => {

            toast.classList.remove(
                "show"
            );

        },
        3000
    );

}


/* =====================================================
   HTML ESCAPE
===================================================== */

function escapeHTML(value){

    if(
        value === undefined ||
        value === null
    ){

        return "";

    }


    return String(value)

        .replace(
            /&/g,
            "&amp;"
        )

        .replace(
            /</g,
            "&lt;"
        )

        .replace(
            />/g,
            "&gt;"
        )

        .replace(
            /"/g,
            "&quot;"
        )

        .replace(
            /'/g,
            "&#039;"
        );

}


/* =====================================================
   CLOSE MODAL WHEN CLICKING OUTSIDE
===================================================== */

document.addEventListener(
    "click",
    function(event){

        if(
            event.target.id ===
            "subCategoryModal"
        ){

            closeSubCategoryModal();

        }


        if(
            event.target.id ===
            "closeCaseModal"
        ){

            closeCloseCaseModal();

        }

    }
);


/* =====================================================
   INITIAL LOAD
===================================================== */

renderTickets();

</script>

</body>
</html>
