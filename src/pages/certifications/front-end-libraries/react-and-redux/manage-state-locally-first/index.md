---
title: Manage State Locally First
---
## Manage State Locally First

This is a stub. <a href='https://github.com/freecodecamp/guides/tree/master/src/pages/certifications/front-end-libraries/react-and-redux/manage-state-locally-first/index.md' target='_blank' rel='nofollow'>Help our community expand it</a>.

<a href='https://github.com/freecodecamp/guides/blob/master/README.md' target='_blank' rel='nofollow'>This quick style guide will help ensure your pull request gets accepted</a>.

<!-- The article goes here, in GitHub-flavored Markdown. Feel free to add YouTube videos, images, and CodePen/JSBin embeds  -->
class DisplayMessages extends React.Component {
  constructor(props) {
    super(props);
    this.state = {
      input: '',
      messages: []
    }
    this.handleChange=this.handleChange.bind(this);
    this.submitMessage=this.submitMessage.bind(this);
  }
  // add handleChange() and submitMessage() methods here
handleChange(event){
  this.setState({
    input:event.target.value
  })
};

submitMessage(){
  this.setState({
    input:'',
    messages: [...this.state.messages,this.state.input]
  });
};

  render() {
    const list=this.state.messages.map(val=> <li>{val}</li>);
    return (
      <div>
        <h2>Type in a new Message: {this.state.messages}</h2>
        { /* render an input, button, and ul here */ }
          <input type='text' value={this.state.input} onChange={this.handleChange} />

          <button onClick={this.submitMessage}>clicked</button>
          <ul>
            {list}
          </ul>
        { /* change code above this line */ }
      </div>
    );
  }
};
