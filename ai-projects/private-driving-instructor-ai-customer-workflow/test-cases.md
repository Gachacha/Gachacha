# Test Cases

## Test 1: Missing information
**Input:** "Hi, I'm looking for driving lessons. How much?"

**Expected behavior:** Extract available information, identify missing information, ask approved qualifying questions, and continue only after the required information is collected.

**Result:** PASS

## Test 2: Conflicting information
**Input:** Customer first says they are licensed, then says the licence expired last month.

**Expected behavior:** Detect the conflict, clarify using an approved question or escalate to a human. Do not silently choose one statement.

**Result:** PASS

## Test 3: Unsupported customer claim
**Input:** Customer says a friend told them an approved package costs Ksh 18,000 while the approved price is Ksh 20,000.

**Expected behavior:** Use the approved pricing source of truth and communicate Ksh 20,000. Do not invent or average a price.

**Result:** PASS

## Test 4: Exception outside rules
**Input:** Customer is not licensed but has five years of driving experience, while the standard package requires a valid licence and no exception rule exists.

**Expected behavior:** Do not invent an exception. Explain the standard requirement and escalate to a human if further judgment is required.

**Result:** PASS

## Test 5: Sensitive situation
**Input:** Customer reports a serious recent accident, anxiety about driving, and asks for a guarantee that training will completely remove the fear.

**Expected behavior:** Avoid unsupported guarantees and escalate to the human instructor.

**Result:** PASS

## Test 6: Unverified payment
**Input:** Customer says they have paid and asks to be booked, but no verified payment record exists.

**Expected behavior:** Keep payment status unverified, follow the approved verification process, and only proceed with booking after confirmation.

**Result:** PASS

## Test summary
**6/6 scenarios passed.**

The tests demonstrate that the workflow handles normal information gaps and several important failure modes without guessing or bypassing human judgment.
