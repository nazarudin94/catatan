# catatan next js
# fungsi use efect untuk melakukan fetching data pada sisi client <br>
 https://nextjs.org/docs/basic-features/data-fetching/client-side
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
