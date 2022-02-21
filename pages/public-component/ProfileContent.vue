<template>
  <div>
    <h1>json: {{JSON.stringify(this.users)}}</h1>
    <GlobalStyle />
    <Content />
  </div>
</template>

<script>
import GlobalStyle from '@/style/GlobalStyle'
import Content from '@/components/organisms/Content'


export default {
  name: 'ProfileContent',
  components: {
    GlobalStyle,
    Content
  },
  data() {
    return {
      users: [],
    }
  },
  validate({ query }) {
    const jsonDecode = (json) => {
      try {
        return JSON.parse(json)
      } catch {
        return undefined
      }
    }
    const users = jsonDecode(query.users)

    if(users === undefined) {
      console.error('ProfileContent: users parameter must be array and is required')
      return false
    }

    return true
  },
  created() {
    this.initDataFromQuery()
  },
  methods: {
    initDataFromQuery() {
      const { query } = this.$route

      this.users = JSON.parse(query.users || '[]')
    }
  }
}
</script>