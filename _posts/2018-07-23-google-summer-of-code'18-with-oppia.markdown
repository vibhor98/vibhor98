---
title: "Google Summer of Code’ 18 with Oppia"
layout: post
date: 2018-07-23 00:30
description:
image: '/assets/images/'
tag:
- gsoc
- oppia
category: blog
author: Vibhor Agarwal
---

![GSoC](../assets/images/gsoc/GSoC.jpeg)

The Google Summer of Code, often abbreviated as GSoC, is an open source initiative taken by Google every year in which the student developers get to work on one of the open source projects during summer and get stipend for their work. This year I was fortunate enough to be a part of GSoC’ 18 under Oppia Foundation. Before diving into the depth of my project, let me take the opportunity to introduce myself: I’m Vibhor Agarwal, a third year Computer Science undergraduate, who loves to contribute to Open Source projects.

![Oppia](../assets/images/gsoc/oppia.jpeg)

Oppia is very special for me from the beginning itself since I love teaching from the childhood and have been interested on the noble cause of spreading education among the masses.

## About the Project

[Oppia](https://www.oppia.org) is the community for both learners and creators where learners can learn lessons effectively and in an enjoyable way while creators can create the effective and engaging lessons. Being a community based on education, it’s super important that the quality of the content is not compromised at all. For the purpose of effective learning of the students, Oppia provides several interactions to interact with the students, provides students effective UI experience and allow different types of input based on the necessity of the question.

My project “New Interactions” aimed at implementing two new interactions- “Number with Units” and “Drag and Drop Sorting” interactions. These interactions will enhance the learning experience of the learners by interacting and helping them in gaining new skills.

## Final Work

**Number with Units interaction** allows the learners to input value along with the mathematical units. The value can be either a real number or a fraction while units can be SI, non-SI or currency units like dollar, rupees, cents etc. This interaction aims at providing the complete understanding of the number (real or fraction) input with mathematical units by directly interacting with the learners. The interaction in the Learner view looks like:

![Number with units interaction in Learner’s view](../assets/images/gsoc/nwu_interaction.png)

The input string is validated at every instant before the final submission of the answer to ensure that the learner enters the units in the correct format.

![Validation of the answer entered by the learner](../assets/images/gsoc/nwu_validation.png)

In the extreme cases when the learner may be stuck with writing units, he can refer to the help table provided with the interaction by clicking on ‘Possible unit formats’ button.

Interactions are associated with the rules in Oppia. These rules are designed to validate the answer submitted by the learner and provide the appropriate feedback accordingly as and when required. Two rules are implemented for Number with Units interaction:

![Rule Editor for Number with units interaction](../assets/images/gsoc/nwu_editor.png)

* **Is equal to** rule: This rule provides appropriate feedback to the learner when the learner submits the exactly same answer as the input provided by the creator of the lesson.

* **Is equivalent to** rule: This rule provides appropriate feedback to the learner when the submitted answer is mathematically equivalent to the input provided by the creator of the lesson. Ex- (2 km and 2000 m), ($2 and 200 cents) are equivalent pairs.


**Drag and Drop Sorting interaction** allows the learner to drag and drop the items and arrange them in either ascending or descending order. This interaction aims at providing good understanding of arranging the things with the help of drag and drop interface. The draggable item can be an image, text, numeric input or a fraction, etc. The interaction in the Learner view looks like:

![Drag and drop sorting interaction in Learner’s view](../assets/images/gsoc/dnd_interaction.png)

It is clear that out of the above items, 2/3 and 4/6 fractions are equivalent and should occupy the same position in the sequence in ascending order. So, they can be dropped so that they somewhat overlap each other as shown while other draggable items shown independently occupy different positions in the sequence.

![Items after sorting](../assets/images/gsoc/drag_and_drop.png)

Four rules are implemented for Drag and Drop Sorting interaction that verifies the submitted answer and provides appropriate feedback to the learner.

* **Is equal to ordering** rule: This rule provides appropriate feedback to the learner when the submitted answer sequence exactly matches with the input provided by the lesson creator. The rule editor in the Creator view where the creator actually sets the input looks like:

![Rule editor for ‘Is equal to ordering’ rule](../assets/images/gsoc/rule3_editor_dnd.png)

* **Is equal to ordering with one item at incorrect position** rule: This rule provides feedback when exactly one item in the submitted sequence is at the wrong position. Its rule editor is same as that of the rule above.

* **Has element X at position Y** rule: This rule provides feedback when the selected element (say X) from the list of elements is at the position (say Y) in the submitted sequence as set by the creator while setting the rules for the interaction. The rule editor in the Creator view looks like:

![Rule editor for ‘Has element X at position Y’ rule](../assets/images/gsoc/rule1_editor_dnd.png)

* **Has element X before element Y** rule: This rule provides feedback when the selected element (say X) from the list is before the another selected element (say Y) as choosen by the lesson creator. The rule editor looks like:

![Rule editor for ‘Has element X before element Y’ rule](../assets/images/gsoc/rule2_editor_dnd.png)

---

## Milestones of the Project

#### Milestone 1:
*Milestone 1.1*
* In this milestone, basic Python configuration file, rule editors and backend object models for Number with Units interaction were added.
* Pull Requests: [https://github.com/oppia/oppia/pull/4950](https://github.com/oppia/oppia/pull/4950); [https://github.com/oppia/oppia/pull/4941](https://github.com/oppia/oppia/pull/4941)

*Milestone 1.2*
* In this milestone, the interaction directives for the Learner’s view were added along with their html templates.
* Pull Request: [https://github.com/oppia/oppia/pull/4979](https://github.com/oppia/oppia/pull/4979)

*Milestone 1.3*
* In this milestone, the two new rule specs, validation of these rules and frontend and protractor e2e tests for the interaction were added.
* Finally, the basic version of the interaction was enabled allowing validation and verification of the mathematical units but without the currency units.
* Pull Request: [https://github.com/oppia/oppia/pull/5028](https://github.com/oppia/oppia/pull/5028)

#### Milestone 2:
*Milestone 2.1*
* In this milestone, basic Python configuration file, two new rule editors and backend objects for Drag and Drop interaction were added.
* Angular ‘ui-tree’ dependency was also added into Oppia.
* Pull Requests: [https://github.com/oppia/oppia/pull/5110](https://github.com/oppia/oppia/pull/5110); [https://github.com/oppia/oppia/pull/5118](https://github.com/oppia/oppia/pull/5118)

*Milestone 2.2*
* In this milestone, the interaction directives for Learner’s view along with their html templates were added.
* Pull Request: [https://github.com/oppia/oppia/pull/5137](https://github.com/oppia/oppia/pull/5137)

*Milestone 2.3*
* In this milestone, two new rule specs, validation for these rules and frontend tests were added for Drag and Drop interaction.
* Pull Request: [https://github.com/oppia/oppia/pull/5162](https://github.com/oppia/oppia/pull/5162)

#### Milestone 3:
*Milestone 3.1*
* In this milestone, currency units (like dollar, rupees, cents etc.) were added for Number with Units interaction.
* Help table for correct input format was also added in case the learner is stuck with writing valid units.
* The final version of the Number with Units interaction was released on the Oppia’s main site.
* Pull Requests: [https://github.com/oppia/oppia/pull/5124](https://github.com/oppia/oppia/pull/5124); [https://github.com/oppia/oppia/pull/5175](https://github.com/oppia/oppia/pull/5175)

*Milestone 3.2*
* In this milestone, two more rule specs for verifing the input were added for drag and drop sorting interaction.
* The two new rule editors and backend objects for these rules were added.
* Pull Requests: [https://github.com/oppia/oppia/pull/5338](https://github.com/oppia/oppia/pull/5338)

#### Bug Fixes
* Fixed the bugs that were discovered in the project during the testing period before the final release.
* [https://github.com/oppia/oppia/pull/5301](https://github.com/oppia/oppia/pull/5301)

---

## Conclusions

Last but not the least, I would like to thank Google for providing this wonderful opportunity to contribute to the open source projects through GSoC, the whole Oppia community for accepting my proposal and helping me through out the program and most importantly my mentor- Prasanna Patil who helped me in every way possible.

Well, I am happy that I learnt so much during this tenure of 3 months. I would like to thank entire Oppia community for this awesome learning experience and I hope to keep my contributions in the future as well.

---

## References

* Oppia Github repository: [https://github.com/oppia/oppia](https://github.com/oppia/oppia)

* All commits to Oppia: [https://github.com/oppia/oppia/commits?author=vibhor98](https://github.com/oppia/oppia/commits?author=vibhor98)

* Accepted proposal: [https://github.com/oppia/oppia/wiki/pdfs/GSoC2018VibhorAgarwal.pdf](https://github.com/oppia/oppia/wiki/pdfs/GSoC2018VibhorAgarwal.pdf)

* Daily devlogs of the work: [https://drive.google.com/open?id=1PHkF7v8lFJASKBMhrXWqODOaaK-ccny7ixmB4A7zkeE](https://drive.google.com/open?id=1PHkF7v8lFJASKBMhrXWqODOaaK-ccny7ixmB4A7zkeE)

