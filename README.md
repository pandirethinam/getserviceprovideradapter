public class ArealistAdapter extends ArrayAdapter {
    List< Carbean> resultValues;

    Context context;

    Carbean itemBean;
    ImageLoader imageLoader;
    public ArealistAdapter(Context context, int resource, List objects) {
        super(context, resource, objects);
        this.resultValues=objects;
        this.context=context;
        imageLoader=new ImageLoader(context);
    }

    public View getView(int position,View view,ViewGroup parent) {
        LayoutInflater inflater= (LayoutInflater) context.getSystemService(context.LAYOUT_INFLATER_SERVICE);
        View rowView=inflater.inflate(R.layout.arealist, null,true);
      //  TextView txtTitle=(TextView) rowView.findViewById(R.id.name1);
        TextView txt1= (TextView) rowView.findViewById(R.id.type);
        TextView txt2= (TextView) rowView.findViewById(R.id.psername);
        TextView txt3= (TextView) rowView.findViewById(R.id.adr1);
        TextView txt4= (TextView) rowView.findViewById(R.id.adr2);
        TextView txt5= (TextView) rowView.findViewById(R.id.subarea);
        TextView txt6= (TextView) rowView.findViewById(R.id.area);
        TextView txt7= (TextView) rowView.findViewById(R.id.city);
        TextView txt8= (TextView) rowView.findViewById(R.id.rating);
        ImageView cinemaPic= (ImageView) rowView.findViewById(R.id.image1);
       // itemBean=resultValues.get(position);

        itemBean=resultValues.get(position);
        imageLoader.DisplayImage(itemBean.getImage(), cinemaPic);
      //  txtTitle.setText(itemBean.getPersonnalname());
        txt1.setText(itemBean.getType());
        txt2.setText(itemBean.getPersonlname());
        txt3.setText(itemBean.getAddress1());
        txt4.setText(itemBean.getAddress2());
        txt5.setText(itemBean.getSubarea());
        txt6.setText(itemBean.getArea());
        txt7.setText(itemBean.getCity());
        txt8.setText(itemBean.getRating());
       // txtGenre.setText(itemBean.getArea());
        //.setText(String.valueOf(itemBean.getYear()));

        return rowView;

    };
}
