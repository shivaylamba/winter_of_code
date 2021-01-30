# Winter of Code - Leaderboard

```jsx
/*react*/
<style>
</style>
<script>
  export default class Application extends React.Component {
    constructor(props) {
      super(props)
      this.state = {
        data: []
      }
    }
    componentWillMount () {
      fetch('https://wocleaderboard-backend.herokuapp.com/getLeaderBoard').then((res) => {
        this.setState({ data: res});
      })
    }
    render() {
    console.log(res);
      return (
        <div>
          <table style="width:100%">
            <tr>
              <th>Github Username</th>
              <th>Score</th>
            </tr>
            {
            this.state.data.map((el) => {
              return (
              <tr>
                <td>{el.key}</td>
                <td>{Math.abs(el.score)}</td>
              </tr>
              )
            })
            }
          </table>
        </div>
      )
    }
  }
```