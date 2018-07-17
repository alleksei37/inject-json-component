<script>
/**
 * How to use:
 * 1. Put any valid JSON on HTML Page and wrap it inside the SCRIPT tag
 * with TYPE="application/json" and content like {"JSON": "object"}. Add ID attribute
 * to this SCRIPT.
 * 2. In your Vue.js Component you can import InjectJson Module
 * and use it with any other arbitrary component which requires data from JSON
 * by simply wrapping your component within InjectJson tag with specified attribute [id].
 * Example:
 * <InjectJson id="uniqueID">
 *  <YourCustomComponent/>
 * </InjectJson>
 * 3. Specify the following property inside a configuration object of your component
 * (<YourCustomComponent/>):
 * {
 * ...
 *  inject: ['json']
 * ...
 * }
 * 4. That's it! Use your JSON data:
 * 4.1. Inside Templates: {{json.field}}
 * 4.2. Inside methods, computed fields and lifecycle hooks: this.json.field
 */
export default {
  /**
   * It takes one attribute
   */
  props: {
    id: {
      type: String,
      required: true,
      default: "jsonTagId"
    }
  },
  /**
   * Share json field with nested components. See Vue.js documentaion about "Provide/Inject" features.
   */
  provide() {
    return {
      json: this.jsonData
    };
  },
  computed: {
    jsonData() {
      const jsonData = document.getElementById(this.id);
      if (jsonData === null) {
        return {};
      } else {
        return JSON.parse(jsonData.innerText);
      }
    }
  },
  render(h) {
    return <div>{this.$slots.default}</div>;
  }
};
</script>
