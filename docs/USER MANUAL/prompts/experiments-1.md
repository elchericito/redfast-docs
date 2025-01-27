---
title: Experiments
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
**Experiments allow you to test variations of a prompt to see which variation results in the greatest positive impact.** You can specify any number of variations within an experiment but at any given point in time only one experiment may run on a given prompt. Over time you may have multiple experiments that have been conducted on a single prompt.

<Image align="center" className="border" border="true" src="https://files.readme.io/f2b3598-image.png" />

An experiment can modify nearly any configuration set on a prompt:

* Title
* Message body
* CTA text and behavior
* Prompt imagery and styling
* 1-Click Actions

Experiment allocations can be set to direct as much or as little traffic as you want to each variation (test group). A percentage of the traffic may be assigned to a Control group in which users within the group are not presented the prompt itself, but are still monitored for conversions against the custom goal.

<Image align="center" className="border" border="true" src="https://files.readme.io/e053b1d-image.png" />

Experiment statistics indicate the number of users assigned to each variation, as well as the number of goal conversions and conversion rate. The z test method is used to determine the statistical significance of the difference between the variation and the control. For this method to produce reliable results, a minimum of 30 users and 5 conversions are required. Furthermore, the larger the conversion rate of the control, the larger will be the number of users required in the variation. For example, for a prompt where the control converts 20% of the users, a minimum of 1000 users will be required in each variation to detect improvement greater than 5%. Because of this, it may take your experiment some time before a winner can be established. Please refrain from drawing conclusions before a winner has been assigned.

Once a winning variation has been determined, you may click on the "Use this" button to end the experiment and update the baseline prompt to match that of the winning variation going forward.

Keep in mind that the z test is not a perfect method for experiments with a large number of variations. The statistical significance only denotes the extent to which that variation is superior to the control not whether the variation is superior to the other variations. In the future, we expect to include Bayesian methods for experiment design.

## Step-by-step

* [ ] Go to Prompts and select the prompt you'd like to experiment with

<Image align="center" className="border" border="true" src="https://files.readme.io/23131d0-Screenshot_2024-04-24_at_18.58.50.png" />

* [ ] Scrol down to the Experiments section and click **+New Experiment**

<Image align="center" className="border" border="true" src="https://files.readme.io/0a15434-Screenshot_2024-04-24_at_19.02.02.png" />

* [ ] Name the experiment

<Image align="center" className="border" border="true" src="https://files.readme.io/d785a04-Screenshot_2024-04-24_at_19.03.27.png" />

* [ ] Add a control (optional)\
  Default setup.\
  By default there is only one variation - the original prompt. If there is a custom goal configured on your original prompt, you can also specify a control. The control will allow you to see whether showing a prompt is making a meaningful impact or not.

<Image align="center" className="border" border="true" src="https://files.readme.io/7c0ec9e-image.png" />

* [ ] Add a variation.\
  A variation is a change to the Original prompt. Changes can be made on most aspects of a prompt including title, message, buttons, appearance, triggers, and actions.

<Image align="center" className="border" border="true" src="https://files.readme.io/bc5027f-Screenshot_2024-04-24_at_19.17.57.png" />

* [ ] Make one or more changes\
  Start by naming the variant based on the change you wish to make, this will allow you to differentiate this variation from others that you may wish to create for the same prompt. Make changes to one or more aspects of this prompt such as the title. To change Actions or Triggers you will need to scroll down to see the settings.

<Image align="center" className="border" border="true" src="https://files.readme.io/c7be6b1-image.png" />

* [ ] Set the percent of traffic to each variation. Total traffic must add up to 100%.

![](https://files.readme.io/f175e0f-image.png)

* [ ] Start the experiment and confirm

![](https://files.readme.io/db1802e-image.png)

* [ ] Review an in-progress experiment

![](https://files.readme.io/5f30ea5-image.png)

<br />

Your experiment is now running and should report click through rates on the variation within minutes depending on your traffic level. The variation with a higher click through rate is one that is performing better. You have the option of allowing the experiment to conitnue to run or you can click on 'Use This' which will replace the control item with the selected variation and end the experiment.  