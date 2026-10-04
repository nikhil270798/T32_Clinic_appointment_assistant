# Clinic Appointment Assistant

## T32 — Chatbots & AI Assistants

An AI-powered clinic appointment assistant developed for the T32 assignment. The chatbot helps users find available doctor appointment slots based on speciality, date/day, and preferred time. It also answers basic clinic FAQs while maintaining a strict safety boundary against medical advice.

## 🤖 Try the Chatbot

**[Open Clinic Appointment Assistant](https://gemini.google.com/gem/1s4BrRrBGn6ZpKmDJtDsjWpbXZ9vqCF40?usp=sharing)**

The chatbot is built using **Google Gemini Gems** and uses the provided clinic Excel workbook as its knowledge source.

---

## 🎯 Objectives

The assistant was designed to:

- Find available appointment slots by **speciality**
- Find slots by **date/day**
- Filter slots by **preferred time**
- Suggest alternative slots when the requested slot is unavailable
- Suggest alternative dates when a doctor is unavailable on the requested day
- Answer basic clinic FAQ questions
- Refuse medical diagnosis, treatment, medication and dosage advice
- Direct emergencies to **108 or the nearest hospital**
- Avoid inventing doctors, appointment slots, fees or clinic policies

---

## 🏥 Clinic Information

**Aarogya Multispeciality Clinic**  
College Road, Nashik

### Doctors

| Doctor | Speciality |
|---|---|
| Dr. Meera Kulkarni | General Physician |
| Dr. Arjun Rao | Paediatrics |
| Dr. Fatima Khan | Gynaecology |
| Dr. Vikram Desai | Orthopaedics |
| Dr. Ananya Iyer | Dermatology |
| Dr. Rahul Joshi | Cardiology |

---

## 📊 Dataset

The chatbot uses the provided Excel dataset containing:

- **Doctors:** 6 doctors
- **Appointment Slots:** 570 slots covering 14 days
- **Clinic FAQ:** 6 FAQ entries
- **Data Dictionary:** Dataset field definitions

The dataset is treated as the **source of truth** for appointment availability.

The assistant is instructed not to fabricate:

- Doctors
- Specialities
- Appointment dates
- Appointment times
- Consultation fees
- Clinic policies

---

## 🔒 Safety Features

The chatbot is explicitly instructed **not to**:

- Diagnose medical conditions
- Interpret symptoms as a diagnosis
- Recommend medicines
- Recommend medication dosages
- Recommend treatment
- Decide whether symptoms are serious or harmless

For emergency situations, the chatbot responds by directing the user to:

> **Call 108 or go to the nearest hospital.**

The assistant can then help with non-emergency appointment scheduling.

---

## 🧪 Testing

The chatbot was evaluated using structured test cases.

### Booking Tests

**20 booking scenarios** were tested, including:

- Exact appointment searches
- Date and time-range searches
- Morning/afternoon requests
- Unavailable appointment slots
- Alternative slot recommendations
- Alternative date recommendations
- Doctor-name searches
- Speciality searches
- Unsupported specialities
- Dates outside the supplied dataset

**Result: 20/20 functionally successful**

### Safety Tests

**5 medical-advice trap scenarios** were tested.

These included requests for:

- Medication and dosage
- Diagnosis
- Treatment advice
- Advice for a child with high fever
- Emergency advice involving chest pain/possible heart attack

**Result: 5/5 passed**

### FAQ Tests

Basic clinic information was also tested, including:

- Clinic timings
- Parking
- Cancellation policy

**Result: 2/2 passed**

### Testing Observation

One minor wording issue was identified: when a user requested an appointment **"after 12 PM,"** the chatbot included the 12:00 PM slot. Since 12:00 PM is exactly 12 PM rather than after 12 PM, this is a minor time-boundary interpretation issue and was documented for improvement.

---

## 📁 Repository Contents

Typical repository files include:

| File | Description |
|---|---|
| `index.html` | Webpage containing a link to the Gemini chatbot |
| `T32_Clinic_appointment_assistant_COMPLETED.xlsx` | Dataset, booking test log, safety test log and AI-use log |
| `T32_Clinic_Appointment_Assistant_Report.docx` | 3–5 page project report with recommendations and reflection |
| `README.md` | Project documentation |

---

## 🚀 How to Use

1. Open the **[Clinic Appointment Assistant](https://gemini.google.com/gem/1s4BrRrBGn6ZpKmDJtDsjWpbXZ9vqCF40?usp=sharing)**.
2. Enter your preferred speciality.
3. Provide a date/day.
4. Provide a preferred time or time range.
5. The assistant will search the supplied appointment dataset.
6. Select from the available options provided by the assistant.

Example:

> I need a cardiology appointment on Saturday, March 7, 2026 between 10 AM and 12 PM.

The assistant will return the available slots matching the request.

---

## 🛠️ Technology Used

- **Google Gemini Gems**
- **Excel** — structured clinic dataset
- **HTML** — simple chatbot access webpage
- **GitHub / GitHub Pages** — project repository and web access

---

## 🔮 Recommendations for Future Improvement

For a production-ready version, the assistant could be enhanced with:

1. **Live appointment integration** instead of a static Excel dataset.
2. **Real booking and cancellation functionality** with confirmation.
3. **Stricter natural-language time interpretation** for phrases such as "after 12 PM."
4. **Automated slot validation** against the scheduling database.
5. **Authentication and privacy controls** for patient information.
6. **Human escalation** for situations requiring clinical judgement.
7. **More extensive safety and adversarial testing.**

---

## 📌 Disclaimer

This chatbot is an **academic prototype** created for the T32 Chatbots & AI Assistants assignment.

It is intended for **appointment discovery and basic clinic information only**. It does not provide medical diagnosis, treatment, medication or dosage advice.

For emergencies, users should **call 108 or go to the nearest hospital**.
