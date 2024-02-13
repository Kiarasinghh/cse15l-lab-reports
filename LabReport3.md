## Part 1

# Bugged Program:

Before:
``
  static int[] reversed(int[] arr) {
    int[] newArray = new int[arr.length];
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = newArray[arr.length - i - 1];
    }
    return arr;
  }
``
After: 
``
  static void reverseInPlace(int[] arr) {
    for(int i = 0; i < arr.length/2; i += 1) {
      int temp = arr[i];
      arr[i] = arr[arr.length - i - 1];
      arr[arr.length-i-1]=temp;
    }
  }
``
The bug was that by the time we got to the last element, changing it to the first one meant not actually changing it’s value. This is because the first element = last element. By only going up to half the length of the array, this issue is avoided as once we get to the middle, all the elements have already been reversed. When there is a odd number of elements in the lis, the element in the middle index wouldn't change in this code, which works with what the function is trying to do. 

# Faliure inducing input:
``
@Test 
public void testReverseInPlace() {
  int[] input1 = {3,4,5};
  ArrayExamples.reverseInPlace(input1);
  assertArrayEquals(new int[]{5,4,3}, input1);
	}
``
The output for the above code should have been 5,4,3 but it ws 5,4,5

![Image](345.png) 


# Succesfull input:
``
	@Test 
	public void testReverseInPlace() {
    int[] input1 = {3,3};
    ArrayExamples.reverseInPlace(input1);
    assertArrayEquals(new int[]{3,3}, input1);
	}
 ``
 ![Image](3,3.png) 

# Part 2 

Chosen command: GREP

## Option 1: -i (case insensitive search)
Example 1:
``
	singh@DESKTOP-VA584UV MINGW64 ~/docsearch/technical/government/media (main)
 	$ grep -1 "legal" 5_Legal_Groups.txt 
	
	BY EDWARD MCDONOUGH
	Five independent Salt Lake organizations that provide legal
	services to the poor, ethnic minorities, seniors and people with
	--
	All," which, until this venture, has been a joint fund-raising
	campaign by an alliance of the non-profit providers of free legal
	services. "And Justice for All," which solicits donations primarily
	from Utah lawyers and foundations, was the first joint fund-raising
	campaign of legal services agencies in the country, and the
	Community Legal Center is the first joint office project of public
	--
	Christenson, pointed out that the shared facility will also be
	efficient for those needing legal services. No longer will a woman
	desperate for a protective order, for example, have to run all over
``
Example 2: 

``
	singh@DESKTOP-VA584UV MINGW64 ~/docsearch/technical (main)
 	$ grep -r -i "doctor"  biomed
	biomed/1471-2156-4-10.txt:        Cynthia Coffman is the post-doctoral associate who
	biomed/1471-230X-1-6.txt:        effects (Figure 1) is striking and indicates that doctors'
	biomed/1471-2334-3-11.txt:        primary care doctors within one week for failure to
	biomed/1471-2334-3-11.txt:        physician and their primary care doctor on admissions. [ 9
	biomed/1471-2334-3-15.txt:        The work is a portion of MA's doctoral thesis. MA
	biomed/1471-2407-3-18.txt:        the chasm between the doctor or health care provider and
	biomed/1471-2407-3-5.txt:        effects and death. Another is that doctors see prognostic
	biomed/1471-2431-3-4.txt:        providers (doctors, lactation counselors, nurses) may
	biomed/1471-2431-3-4.txt:          doctor.
	biomed/1471-2431-3-4.txt:          about the advantages of breastfeeding from a doctor,
	biomed/1471-2431-3-4.txt:          doctor-mediated information, this paper also presents
	biomed/1471-2431-3-4.txt:          (information from anyone, from a medical doctor, from
	biomed/1471-2431-3-4.txt:            doctor or a nurse before the
	biomed/1471-2431-3-4.txt:            doctor before the birth of their
	biomed/1471-2431-3-4.txt:            the maternity ward by either a doctor or a nurse was
	biomed/1471-2431-3-4.txt:            Doctor-mediated breastfeeding information given
	biomed/1471-2431-3-4.txt:          of the doctors did not make specific recommendations on
	biomed/1471-2431-3-4.txt:          mediated by health care personnel (doctor or
	biomed/1471-2431-3-4.txt:          doctor/nurse) influenced the actual duration of exclusive
	biomed/1471-2431-3-5.txt:          doctor, and therefore some of the questionnaires were not
	biomed/1471-2458-2-21.txt:        offices and clinics of doctors with 3 (4.6%) claims.
	biomed/1471-2458-2-25.txt:              take it to the doctor?' "
	biomed/1471-2458-2-25.txt:              better go to the doctor, you know you're suppose to
	biomed/1471-2458-2-25.txt:              go to the doctor but you don't want to go to the
	biomed/1471-2458-2-25.txt:              doctor because the doctor is not private anymore.
	biomed/1471-2458-3-20.txt:        (e.g. staff meetings of ED doctors). Moreover, our results
	biomed/1471-2458-3-9.txt:        that a doctor's recommendation to have breast cancer
	biomed/1472-6793-2-19.txt:        author DER (doctoral candidate) and contributed to the
	biomed/1472-684X-2-2.txt:        suggest different attitudes of doctors and policies of
	biomed/1472-6882-1-12.txt:        case management increases patient-doctor interaction and
	biomed/1472-6882-2-5.txt:        their doctor or pharmacist. The most commonly consulted CAM
	biomed/1472-6920-2-1.txt:          course, Patient-Doctor II [ 4 ] . The course is taught
	biomed/1472-6920-2-1.txt:            patient-doctor interaction techniques (patient
	biomed/1472-6947-1-2.txt:        treatment options with their doctors. A recent study
	biomed/1472-6963-1-8.txt:        who typically received influenza vaccination in a doctor's
	biomed/1472-6963-3-14.txt:            effect when none exists. A doctor who knows that the
	biomed/1478-7954-1-3.txt:        doctors [ 28 ] . An important aspect in the analyzing the

``
## Option 2: -c (count occurences of match)

Example 1:
``
	singh@DESKTOP-VA584UV MINGW64 ~/docsearch/technical (main) 
 	$ grep -r -c "danger" 911report
	911report/chapter-1.txt:3
	911report/chapter-10.txt:2
	911report/chapter-11.txt:23
	911report/chapter-12.txt:17
	911report/chapter-13.1.txt:2
	911report/chapter-13.2.txt:0
	911report/chapter-13.3.txt:0
	911report/chapter-13.4.txt:0
	911report/chapter-13.5.txt:0
	911report/chapter-2.txt:1
	911report/chapter-3.txt:16
	911report/chapter-5.txt:0
	911report/chapter-6.txt:4
	911report/chapter-7.txt:1
	911report/chapter-8.txt:7
	911report/chapter-9.txt:8
	911report/preface.txt:1
``

Example 2: 
``
	singh@DESKTOP-VA584UV MINGW64 ~/docsearch/technical/biomed (main)
	$ grep -c "adult" 1468-6708-3-1.txt
	20
``
## Option 3: -C (display surrounding lines with context)

Example 1: 
``
singh@DESKTOP-VA584UV MINGW64 ~/docsearch/technical/biomed (main)
$ grep -n "lipid" 1468-6708-3-3.txt
19:        these trials did not assess the effect of lipid-lowering
23:        lipid-lowering therapy would provide incremental benefit if
47:        revascularization and change in lipid levels throughout the
81:        for a number of reasons. Although lipid-lowering therapy
102:        lipid-lowing therapy after coronary events.
179:        syndromes regardless of baseline lipid levels. The small
182:        dissect the relationship between baseline lipid levels and
194:        studies suggest that lipid-lowering agents exert short-term
198:        could still make a compelling argument that lipid-lowering
207:        in-hospital initiation of lipid-lowering therapy appears to
209:        19 20 21 ] . Finally, although lipid levels may be
214:        non-pharmacologic lipid-lowering interventions to attain
220:        lipid-lowering therapy from patients who present with an
251:        aggressive vs. earlier lipid lowering therapy.
263:        less aggressive lipid-lowering in
``



