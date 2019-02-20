# Activity Flow Editor

## Goals and Scopes
The Activity Flow Editor is a lightweight reusable Web Component to provide:
1. simple activity-centric representations of [GO-CAMs](http://geneontology.org/go-cam)
2. targeted editing ability (e.g. create an activity and [causally link](https://github.com/oborel/obo-relations) two activities)

Its primary purpose is to be integrated in [Noctua Form](https://github.com/geneontology/simple-annoton-editor) to complete this curation workflow.

## Intended Integration

### HTML side
Ideally, this would resemble this:

```html
...
<head>
  <script src="activity-flow-editor.js"></script>
</head>

...

<activity-flow-editor   usertoken="xxx" 
                        modelid="yyy" 
                        onnewactivity="onNewActivity"
                        onselectedactivity="onSelectedActivity"
                        onnewcausalrelation="onNewCausalRelation"
                        onselectedcausalrelation="onSelectedCausalRelation"
/>
```

### JS side
```js


/**
 * a new activity node was created
 * @param {string} activity_id - The uid of the activity
 */
onNewActivity = function(activity_id) {
    // client-side actions
}

/**
 * an activity was selected
 * @param {string} activity_id - The uid of the activity
 */
onSelectedActivity = function(activity_id) {
    // client-side actions
}

/**
 * two activies were linked by a causal relationship
 * @param {string} activity_id1 - The uid of the first activity
 * @param {string} relation_type - The default type of relation created (e.g. activate or inhibit), can be further refined by a user
 * @param {string} activity_id2 - The uid of the second activity
 */
onNewCausalRelation = function(activity_id1, relation_type, activity_id2) {
    // client-side actions
}

/**
 * a causal relationship link was selected
 * @param {string} activity_id1 - The uid of the first activity
 * @param {string} relation_type - The default type of relation created (e.g. activate or inhibit), can be further refined by a user
 * @param {string} activity_id2 - The uid of the second activity
 */
onSelectedCausalRelation = function(activity_id1, relation_type, activity_id2) {
    // client-side actions
}
```

## Notes
* Best practices for custom web components: https://developers.google.com/web/fundamentals/web-components/best-practices
