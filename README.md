# jekyll-include-chart
A barebones Jekyll plugin to create charts using [chart.js](https://www.chartjs.org/docs/master/getting-started/installation.html) in your posts.


## Installation

- Install chart.js using one of the methods described [here](https://www.chartjs.org/docs/master/getting-started/installation.html).
- Drop the ```include-chart.rb``` into your Jekyll ```_plugins``` directory. That's it.

## Usage

Do something like this in your Markdown files, or wherever you can use Liquid templates:

```
{% include_chart myChart!500!500!{
    type: 'polarArea',
    data: {
      labels: ['Red', 'Blue', 'Yellow', 'Green', 'Purple', 'Orange'],
      datasets: [{
        label: '# of Votes',
        data: [12, 19, 3, 5, 2, 3],
        borderWidth: 1
      }]
    },
    options: {
      responsive: false,
      maintainAspectRatio: false,
      scales: {
        y: {
          beginAtZero: true
        }
      }
    }
  } %}
```

The above will create a ```polarArea``` chart of width 500 and height 500.
Here is a [test page](http://avishek.net/assets/pages/test-page.html)
There are no defaults; you **must** specify the width, height, and configuration. There is no error checking: use at your own risk.

## Warning

This plugin has no error checking, no edge case checking, no configurability.

## Why?

I wanted to integrate chart.js in my Jekyll posts, and the only option was ```jekyll-diagrams```, but that conflicted with my usual ```jekyll-mermaid``` plugin. So I wrote a separate plugin for integrating chart.js.

