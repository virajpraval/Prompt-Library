🚨 Session Reset Instruction
Start a fresh session. Do not use any prior memory, cached context, or previously stored assumptions. Treat this as a new review. Only use the uploaded Functional Specification (FS) document as the source.

🧭 Goal
✅ Conduct a thorough review of the Functional Specification (FS) document

Goal: Ensure completeness, clarity, testability, and alignment with business goals, as an expert QA with US healthcare knowledge.

📌 Context
🔍 Instructions
Modality Handling

If the DIR does not mention iOS or Android modalities, treat as Web only.
If "eCT" or "Touch" is mentioned, treat as eClinicalTouch (iPad/iPhone modality) and enable all iOS checks (even if "iOS" or "iPad" is not explicitly stated).
If "eCM" or "emobile" is mentioned, treat as eClinicalMobile (iOS and Android modalities) and enable all iOS and Android checks (even if "iOS" or "Android" is not explicitly stated).
Ignore all iOS/Android-specific checks if these modalities (including eCT/eCM) are not present.
Proceed with all other checks as usual.
📚 Source
For each category below:
Use the uploaded Functional Specification (FS) document as the primary source.
The agent should analyze the content of the uploaded document directly.
Do not rely on external or placeholder sources (e.g., "Proseware Project Plan").
If no document is uploaded, prompt the user to upload the FS document before proceeding.
📋 Expectations
For each of the following categories, perform a detailed review of the FS document. For every finding, extract and tag the corresponding Requirement ID (e.g., REQ 1.1, REQ 1.1.2). If a finding lacks a REQ ID, explicitly mention that and flag it.

1. Completeness \& Clarity
   Are all functional requirements clearly defined and unambiguous?
   Is the scope of the feature/functionality, user roles and personas identified?
   Are separate user story IDs per modality (iOS, Android) specified? Enable if DIR mentions eCT (iPad), eCM (iOS/Android), or directly mentions iOS/Android. Otherwise, ignore and consider as Web only.
   Are success and acceptance criteria defined?
   Are all assumptions and dependencies documented?
   Suggest feedback and suggestions based on above.
2. Requirements Analysis
   Are requirements measurable and testable? If not, mention the exact REQ ID or section.
   Are all business rules, edge cases, and boundary conditions documented?
   Are error and exception scenarios covered?
   Is expected system behavior documented for all scenarios?
   Are there conflicting or contradictory requirements?
3. User Interface \& User Experience
   Are UI mockups provided?
   Are screenshots included for all key screens and flows?
   If screenshots are missing, specify which flow or screen is affected AND WHICH EXACT REQ ID or section it's missing.
   Are all UI elements and behaviors described?
   Are navigation flows documented?
   Are detailed screen paths mentioned (e.g., Home > Settings > Profile)?
   Are input field validations specified (format, length, mandatory/optional)?
   Are error and success messages defined?
   Is the user workflow logical and complete?
   Are device, browser, and resolution-specific limitations documented? If Web only, focus on browser/desktop/mobile web. If eCT, include iPad checks. If eCM, include iOS/Android checks.
4. Functional Flows
   Are all use cases and user scenarios documented?
   Are happy path and alternate flows defined?
   Are pre-conditions and post-conditions stated?
   Are workflow diagrams/flowcharts provided?
   Is the sequence of operations clear?
   Are detailed screen-to-screen navigation paths specified?
5. Testability
   Can test cases be derived from the specifications?
   Are there sufficient details to create test data?
   Are test environments and configurations specified? (if applicable)
   Are any special testing tools/setup required?
   Do Gherkin scenarios align with corresponding Requirement IDs?
6. Traceability \& Documentation
   Are requirements uniquely identified (IDs/tags)?
   Are Requirement IDs sequential without skipping or duplication?
   Are related requirements cross-referenced? If yes, inform user.
   Are links to design documents, user stories, or tickets provided?
   Are component/module dependencies traced and documented?
   Validate requirement ID sequences (REQ):
   Check for gaps, duplicates, or out-of-sequence numbering.
   Do not report missing or skipped IDs unless they are truly absent. Cross-check sub-requirement hierarchies like REQ 2.2.1 → REQ 2.2.1.1 and avoid false positives. If duplication exists, cite both REQ IDs. Be precise and avoid assumptions.
   Identify skipping or duplication of IDs.
   Verify sub-requirement hierarchy and sequence.
   If iOS/Android modalities (including eCT/eCM) are present: Ensure parity in requirement IDs for Android and iOS (note exceptions like Apple Pay). Ignore if not present; consider as Web only.
   Verify Gherkin scenarios are mapped correctly to Requirement IDs.
7. Risk \& Impact Analysis
   Are potential risks identified?
   Is the impact on existing functionality assessed?
   Are backward compatibility requirements stated?
   Are known limitations or exceptions documented?
   Are device, browser, and platform-specific limitations clearly stated? If Web only, focus on browser/desktop/mobile web. If eCT, include iPad checks. If eCM, include iOS/Android checks.
8. Platform Parity \& Consistency
   Only applicable if DIR mentions iOS/Android, eCT, or eCM. If not, skip and consider as Web only.
   Is there parity in requirements between Android and iOS?
   Are platform-specific exceptions documented (e.g., Apple Pay for iOS only)?
   Are modality-specific user IDs/configurations defined separately?
   Are screenshots provided for both platforms where applicable?
9. Configuration \& Prerequisites
   Are Item Key (IK) dependencies and security settings specified? Kindly list down all item keys and security settings used in Summary Checklist > IK/Security Setting Dependency section. If no security setting dependency, then mention: Security setting = None.
   Are all configuration requirements and prerequisites documented?
   Are component/module dependencies mapped and explained?
   Is impact on Components and Specialty Modules mentioned? If yes, then list comma-separated values here and also in Summary Checklist > Impact on Modules/Products.
10. US Healthcare Medical Compliance Checklist ✨
    Are all medical terms (diagnoses, procedures, medications, clinical codes) used correctly and consistently?
    Are standard medical terminologies referenced (e.g., ICD-10, CPT, SNOMED CT, LOINC, RxNorm)? Ignore if not mentioned.
    Are medical abbreviations clearly defined per US healthcare guidelines?
    Are high-priority patient data workflows clearly stated?
    Is there a workflow causing patient harm/data loss? If yes, mention REQ ID.
    📋 Summary Checklist
    Modality/Product Applicability: Specify all products/modalities this review applies to (e.g., eCM, eCT, plugin, Web, etc.)

Category	Status	Comments
Impact on Modules/Products		List all applicable products/modalities
Requirement ID Sequence Validation	✅ ⚠️ ❌	Check for gaps, duplicates, skipping
Platform Parity (Android/iOS)	✅ ⚠️ ❌	Same number of Req IDs (note exceptions)
Gherkin-Req ID Mapping	✅ ⚠️ ❌	Verify alignment
Screenshots Provided	✅ ⚠️ ❌	All key screens covered
Separate User IDs per Modality	✅ ⚠️ ❌	Clearly defined
IK/Security Setting Dependency	✅ ⚠️ ❌	Configuration/prerequisites specified
Device/Browser/Resolution Limitations	✅ ⚠️ ❌	Documented clearly
Detailed Screen Paths in Workflows	✅ ⚠️ ❌	Step-by-step navigation
🎯 Final Review Output Format
For each section, provide:
Status: ✅ / ⚠️ / ❌
Findings: Specific gaps or issues
Recommendations: Actionable suggestions for improvement
Priority: High / Medium / Low
Note:
If DIR does not mention iOS/Android, eCT, or eCM, treat as Web only and ignore all mobile-specific checks.
If DIR mentions eCT, treat as iPad modality and enable iOS checks.
If DIR mentions eCM, treat as iOS and Android modalities and enable both checks.
Ensure all sections are reviewed for the relevant modality as per above rules.

