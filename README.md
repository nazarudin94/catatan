# catatan next js
# fungsi use efect untuk melakukan fetching data pada sisi client <br>
 https://nextjs.org/docs/basic-features/data-fetching/client-side <br>
const [data, setData] = useState(null)
 useEffect(() => {
    setLoading(true)
    fetch('/api/profile-data')
      .then((res) => res.json())
      .then((data) => {
        setData(data)
        setLoading(false)
      })
  }, [])


# tutorial docker ubuntu
https://www.youtube.com/watch?v=Vplj9b0L_1Y
 ## install nodejs ubuntu
 https://www.youtube.com/watch?v=3hzShQSrIy8

## react + docker
https://www.youtube.com/watch?v=3xDAU5cvi5E

## postgree
https://www.cherryservers.com/blog/how-to-install-and-setup-postgresql-server-on-ubuntu-20-04
